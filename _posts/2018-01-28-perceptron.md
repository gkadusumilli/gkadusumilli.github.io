---
title: "Introduction to Convolutional Network"
date: 2020-01-26
tags: [machine learning, Neural Network, Deep Learning]
header:
  image: "/images/perceptron/percept.jpg"
excerpt: "machinelearning, Neural Network, Deep Learning"
mathjax: "true"
---

In this article, we will understand the concepts of Convolutional Neural Networks (CNN's).

##Filters
* Size of Filter: 3x3 or 5x5 (a rule of thumb)
* We take a filter of the size specified by the user (a rule of thumb is 3x3 or 5x5) and we move this across the image from top left to bottom right. For each point on the image, a value is calculated based on the filter using a convolution operation.

<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/filters.png" alt="filters">

* When building the network, we randomly specify the value for filters, which then continuously update themselves as the network is trained.

<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/feature_map.png" alt="feature map">

##Feature Map
after the filters have passed over the image, a feature map is generated for each filter. These are taken through an activation function.

<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/map1.png" alt="feature map">

##Pooling (POOL)
The Pooling layer (POOL) is a downsampling operation, typically applied after a convolution layer. we can also use pooling layers in order to select the largest values on the feature maps and use these as inputs to subsequent layers.

In particular, **max** and **average** pooling are special kinds of pooling where the maximum and average value is taken.

###Max pooling
<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/max_pool.png" alt="Max Pooling">
* Each Pooling operation selects the maximum value of the current view.
* Max pooling is used to find outliers, preserves detected features.

###Average pooling
<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/avg_pool.png" alt="Average Pooling">

* Each pooling operation averages the values of the current view.
* Ex: Sum (12+20+8+12) resultant value is divided with 4
* Average pooling downsamples the feature map.

##Strides
* For a convolution or a pooling operation, the stride S denotes the number of pixels by which the window moves after each operation.

* Stride controls how the filter convolves around the input volume.

* Let's take 7x7 input volume, a 3x3 filter (Disregard the 3rd dimension for simplicity), and a stride of 1. This is the case that we're accustomed to.

<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/strides.png" alt="Strides">

##Padding
Padding essentially makes the feature maps produced by the kernels the same size as the original image.

Why Padding is Important?

* It is easier to design networks if we preserve the height and width and need not worry too much about tensor dimensions when the transition from one layer to another layer

* Padding allows for designing deeper networks. without padding, a reduction in volume size would reduce too quickly.

## H2 Heading

### H3 Heading

Here's some basic text.

And here's some *italics*

Here's some **bold** text.

What about a [link](https://github.com/dataoptimal)?

Here's a bulleted list:
* First item
+ Second item
- Third item

Here's a numbered list:
1. First
2. Second
3. Third

Python code block:
```python
    import numpy as np

    def test_function(x, y):
      z = np.sum(x,y)
      return z
```

R code block:
```r
library(tidyverse)
df <- read_csv("some_file.csv")
head(df)
```

Here's some inline code `x+y`.

Here's an image:


Here's another image using Kramdown:
![alt]({{ site.url }}{{ site.baseurl }}/images/perceptron/linsep.jpg)

Here's some math:

$$z=x+y$$

You can also put it inline $$z=x+y$$
