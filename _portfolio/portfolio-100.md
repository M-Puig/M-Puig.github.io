---
title: "Special Project at Georgia Tech Lorraine's DREAM Robotics lab - 2020"
excerpt: "<img src='/images/gtl-logo-2019.png' width=200>"
collection: portfolio
---

This Special project, in collaboration with Jackson Crandell, Théo Galizzi and Victor Galizzi, aimed at having a small RC racecar developped by the DREAM Robotics lab to autonomously complete laps around the lake nearby the Georgia Tech Lorraine campus. Another team was working simultaneously on this topic, and we had the constraint of not using deep learning while the other team had to use these techniques.

After various experimentations on types of segmentations, we chose to use Canny Edge detection, and these use the output into a Hough Line transform to get the lines of the road (its outer limits and the central white line).

This is an example of a raw image from the car's camera with the horizon line added
<img src="/images/portfolio-GTL/rawcamera.png" width=300>

The first transformation is to do inverse perspective mapping to obtaine a bird's eye view
<img src="/images/portfolio-GTL/birdseyeview.png" width=300>

Then the canny filter and Hough line transforms are applied
<img src="/images/portfolio-GTL/houghline.png" width=300>

Finally a kalman filter is used to update the positions of the lines with the new observations
<img src="/images/portfolio-GTL/kalman.png" width=300>

A spline curve is the traced using the detected lines to obtain a path for the car. A line following algorithm was then implemented for the car to follow the curve, with appropriate speeds and angles.

Sadly, this project was interrupted by the covid crisis before we could try it out around the lake. However, we had a test environment using AirSim, an open source vehicles simulator based on unreal engine 4. Here is a video of the car roaming by itself on the virtual road.

<video width="640" height="360" controls>
  <source src="/images/portfolio-GTL/AirsimControlDemo.mp4" type="video/mp4">
</video>