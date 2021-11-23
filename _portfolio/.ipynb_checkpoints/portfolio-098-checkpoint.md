---
title: "Neural style transfer - 2021"
excerpt: "<img src='/images/starry_martin.png' width=100>"
collection: portfolio
---

This project is an implementation of [Universal Style Transfer via Feature Transforms (Gatys et
al., CVPR 2015)](https://www.cv-foundation.org/openaccess/content_cvpr_2016/html/Gatys_Image_Style_Transfer_CVPR_2016_paper). The aim is to merge two images, a content and a style image, to produce a new picture that is the content image in the style of the style image. The network consists of a convolutional neural networks that extract features from the content and the style images. the different feature layers are stored, and a white noise image is passed through the network. a linear combination of 3 losses -One content loss, one style loss and a total variation loss- is then used to compute a loss over the white noise image, that is changed through backpropagation. this process is iterated over the output images.

The style loss uses specific feature layers of the style image, and likewise, the content loss uses feature layers of the content image. The additional total variation loss is a regularization term that allows for smoother images by penalizing total pixel variation.

Here is an example with my home city, Montpellier, using Van Gogh's sunflower painting as the style to use. It's a reference to the original paper, that used the authors' city of Tubingen and Van Gogh starry night.

So, from the following to pictures,

<img src='/images/tournesol_montpellier_before.png' width=800>
We get this awesome style transferred image of Montpellier!

<img src='/images/tournesol_montpellier.png' width=512>