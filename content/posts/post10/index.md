---
title: "Journey into synthesizers"
summary: Music, DIY
date: 2024-08-15
image: analog_head.png
description: " My journey into analog synthesizers & ambient music"
---

Growing up playing 8-bit retro games and being looped into hours of RPG's, drew me into background scores and instrumentals more than I expected. I never had any experience around learning or playing musical instruments as a child which further pushed me away from creating instrumentals. It was only after getting into electronics as a hobby, I started questioning more into how the sounds in film scores and games were made. Some of them were just a series of sequences patched with effects to create soothing and evolving soundscapes. This gave me some confidence to see where I can go with making compositions of my own. Also the start to a VERY expensive hobby I did not know I was getting into.

{{<bundle-image title="Volca Keys" name="analog1.jpg" >}}
My first mono synth which is still around now.

{{<bundle-image title="Adapting Volca for Eurorack" name="analog2.jpg" >}}

Added a 9V voltage regulator to step down from euro levels (12V) and an inverting op-amp to match with eurorack levels (since Volca Keys outputs at line level which is much lower as compared to eurorack level +10V pp). The documentation of this can be found [here](https://www.grappendorf.net/projects/eurorack/korg-volca-panels.html). All credit to Grappendorf for the 3D printed eurorack mount and schemtics for the Volca.

{{<bundle-image title="Eurorack Case & Custom modules" name="analog3.jpg" >}}

To avoid breaking the bank, I used a bathroom cabinet case from [søstrene grene](https://sostrenegrene.com). This is currently not available, but I guess any bathroom cabinet with a bit of DIY tools can be used to create a 84HP 6U rack mount (1hp is 5.08mm, 1U is 44.45mm). For eurorack rails, there are many alternatives such as [nVent SCHROFF Horizontal Rails ](https://uk.rs-online.com/web/p/rack-rails/2838401?gb=a) which you can get from RS UK (where I am based currently). And lastly for the power supply a cheap MeanWell Power supply RT-65B from AliExpress giving +12V, -12V & 5V should do the job for the amount of modules going into the rack. The breakdown for the cost of this is further down in the post. The finished rack as seen below.

{{<bundle-image title="Volca, NTS-1 & utility modules" name="analog4.jpg" >}} 

Also made a eurorack mount for the Korg NTS-1. I will post the gerber files for these on here. At the end, made a few tracks on these, but I wanted different layers and sounds and this began my obsession for the hobby.

{{<bundle-image title="Mother of all Synths- MOOG" name="analog5.jpg" >}} 

First big spend and was lucky to get this one cheap.

{{<bundle-image title="Current Setup" name="analog6.jpeg" >}} 

My current setup took a bit of time to get right, essentially since there were some devices that were 5V powered and giving line level output (which meant improper gain staging when chaining with eurorack level signals from the Moog Mother-32 and Dreadbox Erebus). Hence I had to borrow a mixer from my friend which took the outputs of the all the synths separately and preamp them accordingly. The resulting cost of my eurorack setup is shown below. I was quite lucky to get some of the modules like the mixer for free and the other heavy synths for a massive discount on marketplace. My skills in electronics and making pcb perfboard prototypes also saved a lot of money.


| **Item**                | **Cost** |
| ----------------------- | ---- |
| Søstrene cabinet        | £30  |
| nVent rails             | £30  |
| PSU                     | £20  |
| Bus Board x2            | £20  |
| Mother-32               | £280 |
| Behringer CU1A          | £38  |
| Volca-Keys              | £70  |
| NTS-1                   | £63  |
| Korg SQ-1               | £75  |
| Dreadbox Erebus         | £201 |
| DIY mix + Amp           | £60  |
| **Total**               | £887 |