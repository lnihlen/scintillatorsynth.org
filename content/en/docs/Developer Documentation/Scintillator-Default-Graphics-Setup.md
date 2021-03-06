---
title: Scintillator Default Graphics Setup
linkTitle: Scintillator Default Graphics Setup
weight: 5
description: Background information on computer graphics and the Scintillator pipeline
---
<!-- generated file, please edit the original .schelp file(in the Scintillator repository) and then run schelpToMarkDown.scdscript to regenerate. -->
###### See also: <a href="{{< ref "/docs/Guides/Scintillator-User-Guide" >}}">Scintillator User Guide</a> 



### The Graphics Pipeline
---



Much like audio programming, graphics programming is a highly specialized field with the opportunity for a lifetime of learning in domain-specific knowledge and experience. Scintillator presents a simplified view of the process of producing real-time graphics on modern graphics architectures, both to keep the metaphor to SuperCollider audio programming intact and to avoid cluttering the interface with less beneficial detail. What follows here is an overview of the different stages of producing images that are exposed to Scintillator for manipulation. Much has been simplified or omitted, please refer to the Further Reading section below for more detail.



#### Rendering Architectures



The gold standard for visual quality in computer-generated imagery has long been a body of technique called <em>ray tracing</em>, which models individual rays of light interacting with a visual scene consisting of mathematical descriptions of shapes and the reflective and absorbative properties of their surfaces. However, until recently ray tracing has been considered too computationally expensive to perform at real-time frame rates necessary for simulations, video games, and video synthesis. Instead, thanks largely to the commercial success of video games, a body of techniques and supporting hardware and software has emerged under the umbrella term of <em>real-time rendering</em>. While ray tracing is inspired by physics, and seeks to model light and its interactions with the materials in a scene, rendering is much more pragmatic and is concerend with generating realistic imagery on a tight performance budget.



The rendering of a scene consists of a series of one or more <em>render passes</em>, the input of which is typically some geometric model describing points, lines, or polygons, and the output of the pass is individual pixel colors stored in a two-dimensional image buffer, intended either for manipulation by subsequent render passes or <em>presentation</em> to the user on the screen. Modern graphics hardware has to operate quickly at vast scale in order to maintain an acceptable frame rate. For example, a modern high-definition 1080p display is 1920 pixels wide by 1080 pixels tall, giving a total of just over <em>2 million</em> pixels that the GPU must compute the color for in under 17 milliseconds at 60 Hz. This means that a modern GPU must perform <em>124 million</em> pixel color computations a second. Rendering engines on modern video games perform multiple render passes and each render pass contains a small program that must be exectued at every pixel, quickly raising the compute costs of rendering to the astronomical.



In order to scale to high resolutions modern GPU (Graphics Processing Unit) architectures are massively parallel, with the high-end discrete GPUs capable of executing thousands of independent threads simultaneously to calculate individual pixel colors. This is a scale much different then the typical CPU, where a high-end CPU might offer 8 cores supporting up to 16 simultaneous threads of independent execution at a time. In order to support such massive paralellism yet remain cost-effective GPUs process information in a fixed series of stages called a <em>graphics pipeline</em>, which comes with some assumptions about the flow of information from one stage to the next and makes many assumptions about the kind of information being processed and the nature of the computations peformed. The trend in graphics programming has been over time to radically increase the flexibility of the graphics pipeline to allow for a broader variety of different kinds of computations to be performed, but GPUs remain significantly more specialized than the general-purpose CPU most programming gets performed on.



There are several more stages to a modern pipeline than detailed here but we will discuss only the stages the Scintillator allows for creation of <a href="{{< ref "/docs/VGens/VGen" >}}">VGen</a>s in.



### Further Reading
---



Here is a collection of links to reference documentation in Scintillator, as well as a few other sources that might be helpful in deepening your understanding of computer graphics.

