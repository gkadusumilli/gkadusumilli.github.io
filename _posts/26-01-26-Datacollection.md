---
title: "Suggestions for Data Collection"
date: 2020-01-26
tags: [Data Collection, Data Processing, Input, CNN]
header:
  image: "/images/Data_collection/Data_header.jpg"
excerpt: "Data Collection, Data Processing, Input"
mathjax: "true"
toc: true
toc_sticky: true
sidebar:
    nav: sidebar-sample
    
---
Many Lessons can be learned from experience in data collection. The following suggestions are written based on my experience which might enhance and facilitate data collection, although they are not inclusive.

1. **Plan Ahead**: Planning plays a pivotal role to curb resource usage and unexpected outcomes. This could begin by practice or pre observing the data, watch for unusual circumstances, and consider how they will be handled. when data already been collected by someone else, be sure to spend more time converting the data into a usable format.

2. **Analyze the data**: Try to analyze the data as they are being collected. Monitor whether the data being collected is adequate to provide the distributions needed as input to the model. check whether any data being collected is redundant to the model. There is no need to allot memory for redundant data.

3. **Check for Homogeneous Data**:Try to combine homogeneous data. check data for similarity. For example, when you want to train a classifier and you want to collect data (images) to train the classifier. make sure your data is free from duplicate images since homogeneous data causes an underfit model.

4. **Data Visualization**:To Discover whether there is a relationship between input samples, build a scatter plot. Sometimes an eyeball scan of the scatter diagram will indicate a relationship between two variables of interest.

5. **Train_Test_Split**:Keep in mind there is a difference between test data and train data, and be sure to maintain separate data for training and testing. you run calculations on the training set to determine various coefficients. You can then use the testing set to check how well the predictions do on a wider set of data, and that gives you information about false positives and false negatives.
