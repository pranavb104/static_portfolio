---
title: "White-Table"
summary: Interactive,Prototype
date: 2019-06-29
image: wt_head.jpg
description: "Designing the experience and framework for interactive storytelling and presentations via objects on the White table"
---

In this project, I was responsible to lead the redesign of [White Table WT2.0](https://www.wtinteractive.com/capgemini), which is a device for storytelling & presentations in enganging and playful ways using physical objects & RFID tech. 

{{<bundle-image title="WT 2.0" name="wt_1.png" >}}

## Process
The initial interactions with the team and current clients was to understand how they used the product in different scenarios. By attending workshops and _market_ days I mapped all the pain points mentioned by them. The most annoying bit was to setup the interactive projector and calibrate the sensor which was difficult for the users who did not have a deep understanding of the technology. 

On the other hand, the product really helped users tell stories in a non-linear way and the use of projection mapping and objects brought a sense of magic to the people in the room.

{{<bundle-image title="market days" name="wt_2.jpg" >}}

There were essentially two parts to this project; one was the ergonomics behind the product and the other was the underlying interaction and how to augment it. I focused more on the interaction part of the project. 

I took a slightly different approach to understand the _magic_ behing projection mapping, I looked at the different kinds of content and objects used while presenting on the white table. The following questions came about ->
1. What if projectors could give physical objects a digital dimension?
2. What if individual objects/artifacts could add depth to storytelling?

{{<bundle-image  name="wt_5.png" >}}

I then ran a series of experiments to understand and explore the different affordances of interacting with projected surfaces. While the original WT2.0 used different objects to tell a story, a white _empty_ object brought a lot of possibilities for interacting with projected surfaces using _rotation_ and _tilting_ to trigger an animation or sequence while giving the object a different form through projected content. These objects could also be used to add depth to storytelling and help zoom in-out of a presentation.

{{<video src="wt_v.mp4" >}}
{{<bundle-image title="Interaction Experiments" name="wt_2.png" >}}

## Object Tracking
These experiments eventually led to building a device which could recognize objects on a surface and dynamically project the content. To see if this is feasible , I tried using pure machine vision (using just a camera) to segment the body from the table surface and then eventually went for a mixed depth-camera tracking system.

{{<bundle-image title="ML Object Tracking" name="wt_3.png" >}}
{{<bundle-image title="Depth Based Tracking" name="wt_4.png" >}}

## Proof of Concept 
A video demonstrating the look and functioning of the prototype.

{{< vimeo id="268555005" >}}

## Where did this project lead to?
This proof of concept was then showed to prospective clients and investors, but eventually did not turn into a mature product. 