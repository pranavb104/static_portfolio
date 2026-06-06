---
title: "Off-Grid BirdNet"
summary: DIY, Birds
date: 2026-05-30
image: botg_head.png
description: "An off-the-grid raspberryPi bird-sound detector using the open source BirdNet model, enclosed in a small portable case"
---

# Bird-off-the-grid
An off-the-grid Raspberry Pi bird-sound detector. The pi is powered by an external battery and solar panel setup along with a wittyPi 4 mini as a HAT to sequence startup-shutdown sequence to ensure the Pi runs at specific times.

{{<bundle-image title="setup" name="botg.png" >}}

## Why did I want to make an Off-Grid BirdNet ? 
While there are already tools like [BirdNetPi](https://github.com/Nachtzuster/BirdNET-Pi) & [BirdWeather](https://www.birdweather.com/shop-birdweather-puc) to detect birds, I wanted to build something where the processing happens locally and that can be easy to setup. Once built, this relatively small offgrid setup could be handled by anyone to record birds at any given location using a simple setup guide. 
The biggest challenge when building this project was justifying whether this could run for a significant time period (off-grid) for detecting birds in the local vicinity. While using the original BirdNetPi, I saw that certain birds usually come at specific times of the year and the detections usually stay consistent for that time and change over the months (not weeks). Another reason being, I had places like the allotment or the park near me where I wanted to know what birds come in those areas and what the difference in landscape brings to the diversity in birds. 

## What does this setup consist of ? 
Since I am based in the UK, I have provided a link for items accordingly. 
1. RPI 3B+ or greater (*Pi 3B+ draws the least amount of current at load -> 0.45A*)
2. WittyPi 4 [Mini](https://thepihut.com/products/witty-pi-4-mini-realtime-clock-and-power-management-for-raspberry-pi) or greater
3. [Waveshare Solar Power Module D](https://thepihut.com/products/solar-power-manager-module) 
4. AOM5024 / EM272 condensor [mic](https://micbooster.com/)
5. RPI usb audio [adapter](https://thepihut.com/products/usb-audio-adapter-works-with-raspberry-pi)
6. PG7 Black Nylon Cable [Gland](https://www.switchelectronics.co.uk/products/pg7-black-nylon-cable-gland-ip68) IP68
7. Short Push Button [Switch](https://www.switchelectronics.co.uk/products/vandal-resistant-off-on-momentary-19mm-ultra-short-switch-spst)
8. Waterproof On-Off Round Rocker [Switch](https://www.switchelectronics.co.uk/products/waterproof-on-off-round-rocker-switch-ip68-spst-10a-250vac)
9. Battery 6x21700 [4000mAh](https://www.nubattery.co.uk/)
10. 21700 3.7V 6P no-solder [housing](https://www.18650.lt)
11. [Waterproof Junction Box](https://www.ebay.co.uk/itm/363436154050?) 

Link to wire condensor [mic](https://github.com/mcguirepr89/BirdNET-Pi/discussions/39) if you do not want to buy an expensive mic
Link to assemble housing [battery](https://www.youtube.com/watch?v=22zPvxZxEwM) 

## How long can the setup run ?
I have tested this in the winter & summer where the solar panel was placed facing the south. The RPI+WittyPi4 mini setup allows to set wake-up & sleep cycles for the pi to save on battery. I mainly set it to 2hrs near Dawn & 2hrs at Dusk and got the following results. 
In the summer (as of May 2026), I was able to run it for **2 weeks** with a mix of grey and sunny skies (It could have gone longer but I did not push it as it wasn't necessary)
In the winter, I could get it to run for **1 week** until the wittyPi low voltage detector set in and put it to sleep. 
I could have added a bigger battery and solar panel , but doing so would make the setup really bulky and heavy to carry around, but doubling the capacity can definitely get in more hours and days of detection. 

## Software
To keep things lean and not processor hungry, I (with the help of Claude) made a new front-end and back-end trimming it down to bare essentials for detection. See documentation [here](/docs/Technical_Architecture.md) and installation docs [here](/docs/Installation.md). 

### Setup screen
{{<bundle-image title="wittyPiSetup" name="wittyPiSetup.png" >}}

Once connected to the RPI Access Point, the interface shows to setup the date to start/end recording and on/off times. Once set the system can be kept on or switched off to save power and only switches on at the times specified in the script. 

A simple one page interface of the recordings can be seen [here](https://drive.google.com/file/d/1I5Lhnq5n_rv88q3N0buTzOPbZwKreb7I/view?usp=sharing) 
 