---
title: "MRPi"
summary: Interactive,Prototype
date: 2020-06-29
image: mrpi_head.png
description: " A Mixed-Reality projection device using just the small and powerful RPI Zero2W"
---

I had this idea of building a portable smart projector which resembles a flashlight based on one of my previous projects.This device could possibly be used for retail settings, giving people a unique way to interact with static content as opposed to viewing it from screens which can be bulky and expensive to setup. This experience could also make way for interactive games and other kind of explorative projects. 

## Software 
It is built inside openFrameworks (C++ framework). It took a bit of time to make and link the open-source libraries together (big shot-out to (jvcleave)[https://github.com/jvcleave/ofxOMXPlayer] for wrapping OMX into OF). It uses the RaspberryPi camera to detect markers (also known as fiducial markers) and play content (videos/gifs/images). The markers themselves can be quite small if the camera is fitted with the right lens and is positioned well with respect to the projector. Markers are a good start to have a dynamic animated projection since their design can be altered to represent a word/phrase making it unique to the person interacting with it. Having him/her interact with any static content makes the experience immersive and present information in a cool way.

{{<bundle-image title="Alpha Prototype" name="mrp1.jpg" >}}

## Hardware
The first alpha prototype embodies a 320x240 LCD projector, RPI 3B+ and camera. I chose the RPI because it has a GPU dedicated for the camera and video player, making it very power efficient and potentially making it possible to have a battery embedded in later versions. It includes a 3D printed case with a button and a handle for ease of use. 

{{< vimeo id="691291081" >}}

## Working
The projector can detect fiducial markers within a 1-1.5m range only in a relatively bright setting. (if the environment becomes too dark, then the content also needs to light up the fiducial to let the camera see it. This can be adjusted and is not a big problem). 

{{<bundle-image title="Beta Prototype" name="mrp2.jpg" >}}

## Revisions for next Iteration 
New RPI Zero 2W in a much smaller package compared to its predecessor combined with a DLP projector which sits as a hat on the PI zero. I made a custom PCB for the hat which would make this a tiny package altogether, also giving enough room to fit in a LIPO battery and making it a portable smart flashlight device 

{{<bundle-image title="Custom PCB" name="mrp3.jpg" >}}

Will post more pictures soon :D

