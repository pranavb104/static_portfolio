---
title: "Pixel Birds Loras"
summary: AI, DIY
date: 2025-03-23
image: pxb_head.jpg
description: "How I generated consistent pixel art style birds"
---

This started from the off-the-grid birdnet [project](https://github.com/pranavb104/bird-off-the-grid). I wanted a small repository of images of different types of birds. I did not want them to be high-res pictures, but something along the lines of pokemon [sprites](https://pokemondb.net/sprites). They all have a set viewing perspective, white background, and are small in size perfect for quick loading (and a lot cuter IMO). 

## Why not use Nano-banana ?
Nano-banana 2 and pro are one of the best models currently (March 2026) that adhere to prompts and generate high quality images. I did try to use Nano-banana 2 to generate images with prompts such as ->
```
positive = (
    f"{bird_name},three quarter front view, pixel art style,low-res, blocky,  "
    "16-bit graphics, white background, minimum details, centered composition, 1024x1024px, less colors"
)
negative = (
    "sloppy, messy, blurry, noisy, highly detailed, ultra textured, "
    "high-resolution, photo-realistic"
)
```
While this gave very good results, the consistency of pixel art style across the images were slightly different. Some of them had black borders, while some of them had a higher degree of pixelization. If I want to have bird sprites, I would like all of them to be of a similar style and quality. Another point being, Google's models are not on the cheap side, generating 50 images cost me ~3.5£ which would eventually break the bank for 6000+ species. 


{{<bundle-image title="GoldCrest" name="goldcrest.png" >}}
{{<bundle-image title="european-starling" name="european-starling.png" >}}

As with the above images, same prompts, but giving slightly different style of images, no way to control it.
In order to get better and consistent results, I decided to try out ComfyUI SDXL models. 

## IP-Adapter to lock in style
I managed to create one image from Nano-Banana 2 I really liked the style of and tried to use that as an input for the IP-Adapter plugin. IP-Adapter essentially locks in the style of the input image and outputs a model fed to the K-sampler. You can increase/decrease the strength of the style by changing the *weight* & *weight_type* parameter. In the K-sampler , I also kept the seed constant to ensure my parameter edits are working towards the same type of bird post/style. But even with all of this, it was impossible to get different birds in the same pose. Also, with larger prompts the models were hallucinating and giving very weird results. 

{{<bundle-image title="IP_ADP" name="ip-adp.png" >}}

## Control-Net Canny to Lock Pose
I thought, if creating consistent poses was a problem, then why not lock in a pose for different kinds of birds. Obviously this meant, figuring out all the different shapes and sizes and categorizing them before feeding it into Control-Net Canny. This [website](https://www.allaboutbirds.org/guide/browse/shape) was really helpful. I tried it out for a few different categories and it was working really well until I had to prompt for birds with very different features and colors. Even prompting it for special features gave distorted results and I was stuck again.

{{<bundle-image title="Canny" name="canny.png" >}}

## Training my own LORA
My last option was to generate a training dataset and create a Low Ranked Adaptation to clip the base SDXL model and have a much simpler workflow to prompt different species of birds. I once again used Nano-Banana 2 to generate 30 images of birds which I liked and all similar in style with a 1024x1024px aspect ratio(since base SDXL model uses the same aspect ratio). Wrote a precise text description for each of the trained images of what I saw (not the same as the prompt). Used [Kohya_SS](https://github.com/bmaltais/kohya_ss.git) GUI to train it with the following parameters (fill them in the GUI and hit train!) ->
```
--pretrained_model_name_or_path="sd_xl_base_1.0.safetensors" \
--train_data_dir="./lora-project/img" \
--output_dir="./lora-project/model" \
--resolution="1024,1024" \
--network_module=networks.lora \
--network_dim=64 \
--network_alpha=32 \
--learning_rate=1e-4 \
--max_train_epochs=10 \
--mixed_precision="bf16" \
--optimizer_type="AdamW8bit" \
--cache_text_encoder_outputs \
--network_train_unet_only
```
I also included a trigger word "pxb bird"  in the GUI to trigger the LORA everytime I write a prompt.

Once training is done, choose the last three models to try out since there might be ones which are under/over fit. You need to experiment with each to see which one gives the most consistent type of images with your prompts. This is how the final flow looks like. 

{{<bundle-image title="final-flow" name="final-flow.png" >}}

The LORA produced the best results with over 80% of the images coming out correct. I noticed that for some specific species of birds like ducks,goose and a few others it could not get the correct color on the body part. This should be probably be re-fed into the training data to create a complex style LORA. 

{{<bundle-image title="common-blackbird" name="Common-blackbird.png" >}}
{{<bundle-image title="Cormorant" name="Cormorant.png" >}}
{{<bundle-image title="Great Egret" name="great-egret.jpeg" >}}

I will post a repo of all the UK birds in pixel art lora style in my birdnet github [repo](https://github.com/pranavb104/bird-off-the-grid)
The next steps would be to create a better LORA using FLUX1.dev, as this model gives much better prompt adherence and is a bigger model to SDXL giving good results overall. 

All project related files (ComfyUI JSON flow, LORA & python script for automating comfyUI generation) can be found [here](https://drive.google.com/drive/folders/1b-irfG-haghWmQohNceLr3OJRXh04Mhx?usp=sharing)
 