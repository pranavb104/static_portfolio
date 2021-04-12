---
title: "White-Table"
summary: Interactive,Prototype
date: 2019-06-29
image: wt_head.jpg
description: "Designing the experience and framework for interactive storytelling and presentations via objects on the White table"
---

In this project, me and my team had to redesign the experience around the original White Table product , which is a device for storytelling/presentations using objects. The table recognizes objects via RFID and in that manner provides a unique experience for people to present their stories in enganging and meaningful ways.

{{< figure src= "/archie/whitetable/wt_1.png" width= "800" title="WT 2.0" class="contentImgBig" >}}

## Design Process
I initially began researching and playing around with the whitetable, to only relaize that projection mapping was most uniquely the "magical" aspect of the product. To explaing this vision of projectors as the future of lighthing and giving objects a digital dimension, I made a series of prototype experiments to validate my thoughts. 

{{< figure src= "/archie/whitetable/wt_5.png" width="800" title="" class="contentImgBig" >}}

{{< figure src= "/archie/whitetable/wt_2.png" title="Mapping Experiments" class="contentImgBig" >}}

## Object Tracking
The experiments eventually led to building a device which could recognize objects on a surface and dynamically project the content. To see if this is feasible , I tried using ML Vision libraries to segment the body from the table surface and then eventually went for a depth-based tracking system.

{{< figure src= "/archie/whitetable/wt_3.png" title="" class="contentImg" >}}
{{< figure src= "/archie/whitetable/wt_4.png" title="Depth Based Tracking" class="contentImg" >}}

## Proof of Concept 
A video demonstrating the look and functioning of the prototype.

{{< vimeo id="268555005" >}}
