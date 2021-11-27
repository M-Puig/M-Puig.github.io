---
title: "Deep Learning for cyclonic andprecipitating object segmentation - Météo France - 2019"
excerpt: "<img src='/images/meteofrance-logo.svg' width=100>"
collection: portfolio
---

Météo-France operationally produces fine-scale precipitation forecasts, based on the numerical weather prediction model AROME. In order to extract some useful information from these forecasts, an algorithm is currently run to detect and characterize precipitating objects (defined as area where the precipitation distribution is homogeneous) based on their intensity (low, moderate and heavy rainfall). 
The goal of aim of my research was to research a new method based on Deep Learning for the detection of these precipitating objects. The method chosen is a convolutional neural network inspired from the U-Net architecture (Ronneberger et al., 2015). I first trained the network on the objects provided by the existing algorithm, in order to examine its ability to reproduce the current results. I then fine-tuned the network with manually annotated maps by experts, so that is would detect and characterize precipitation patterns based on intensity but also texture (continuous ou discontinuous).

Example of a Western european rainmap segmentation, bottom left (b) is the automatic segmentation and bottom right (c) the manual one.
<img src='/images/meteofrance-texture.png' width=400>

I also used transfer learning to adapt the network to the rain patterns of the French overseas regions of Matinique and Guadeloupe, as well as the broader area of the Caribbean, where less data was available.

Example of segmentation over the Caribbean. (a) is the network trained over western europe, (b) is the fine-tuned network, and (c) is the manual annotation.
<img src='/images/meteofrance-intensite-antilles.png' width=500>

Considering the encouraging results we obtained, I then started working on segmenting tropical cyclones in the caribbean. Fro that, we had two channels in our maps, a wind map and a 850pa geopotential height map (which determines pressure levels). They are comprised of two areas and one spot, the cyclonic winds area, the maximal winds area and the eye of the cyclone. For the two areas I used the same U-net architecture, and for the eye of the cyclone, a modified version that would output the pixel coordinates of the eye. 

<embed src="/files/poster_meteo_france.pdf" width="1000px" height="1400px" type='application/pdf'/>
