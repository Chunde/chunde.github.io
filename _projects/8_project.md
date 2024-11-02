---
layout: page
title: A Fast Implementation of HOG for Object Detection
description: State-of-the-art real-time HOG implementation
img: assets/img/HOG.jpg
importance: 2
category: Research
# giscus_comments: true
---

## Introduction
I presented an optimized method for calculating the Histogram of Oriented Gradients (HOG) descriptor, which is widely used in computer vision for object detection, particularly in human detection tasks. Traditional HOG calculation methods are computationally intensive, especially when applied to real-time processing tasks.

This is an efficient approach that combines a lookup table with an integral image technique to significantly speed up HOG computation. By using lookup tables, the method precomputes gradient values, reducing the need for repetitive calculations during feature extraction. Additionally, by utilizing the integral image technique, the method quickly accumulates pixel intensities over regions, making it possible to compute block-based histograms more rapidly.

The proposed method achieves a substantial increase in processing speed compared to standard HOG implementations without compromising accuracy, making it suitable for real-time applications. The results demonstrated in the research show that this approach maintains detection performance while achieving computational efficiency, offering a valuable advancement for systems requiring fast, reliable object detection.


## Demon Video
* In this video, you'll see an overview of my development environment, the preparation process for the training dataset, and additional relevant information.


<iframe width="720" height="480" src="https://www.youtube.com/embed/xMS9eZ2HjLA?si=IGeSM-tOXXLrdpgd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>