---
title: "Object detector Framework"
date: 2021-02-08
header:
  image: "/images/notebook.jpg"
excerpt: "GPU, Colab"
mathjax: "true"
toc: true
toc_sticky: true
sidebar:
    nav: sidebar-sample


Prior understansing about the object detection systems like **R-CNN**, **SSD** and **YOLO**, we should know the 
common similarity (standard approach) used to detect objects and metrics defined to evaluate the performance of the object detection model.

### The Object detection models mainly has four components

**1. Region proposal**

**2. Feature extraction and network predictions.**

**3. Non-maximum supression (NMS)**

**4. Evaluating Object detectors**

Let's begin

### 1. Region proposals

![RP](/images/region_proposals.jfif)

Region proposals algorithm genrates multiple Region of Interest (RoIs) assuming high likelihood of containing an object. Each generated bounding boxes has an **objectness score**.

Bounding boxes with high value of objectness score are then passed to next layers for further processing and RoIs with lower objectness scores are discarded.

**Approches to generate region proposals**

> 1. Selective search algorithm

> 2. Extracting the features through Deep neural network to generate regions.

Region proposals produces a lot of bounding boxes to be further analyzed and classified by the network. During this step, the network
analyzes these regions in the image and classifies each region as ***foreground (object)*** or ***background (no object)*** based on its objectness score.

if the objectness score is above a certain threshold, then the region is considered a foreground and pushed forward in the network.

**Trade-off with generating region proposals**

* <ins>If the threshold is too low</ins> the network generates all possible proposals, we will have a better chance of detecting all objects in an image but this comes with a computational cost and will slow down detection.

* <ins>If the threshold is high</ins> the network may generate less proposals which may not produce the desired results.

The right approach is to use problem-specific informations to reduce the number of RoIs

### 2. Network predictions


2. Determining the location of the object.
    
To evaluate the performance of the object detection model, we look for two metrics **Frames per second** and **mean average precision (mAP)**.

### Frames Per Second (FPS) to measure detection speed.

FPS metric is used to measure the detection speed. For example, Faster R-CNN operates at 7 FPS, whereas SSD operates at 59 FPS.Higher the speed better the model for deployment.

### Mean Average Precision (mAP) 

When we study research papers we often see mAP score while evaluating the performance of the model. Let's know more about this metric

mAP metric has a scale from 0 to 100, and higher the mAP values are typically better. This metric value is different from the accuracy metric in classification tasks.

Prior understandinf 
