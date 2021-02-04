---
title: "All about Confusion matrix"
date: 2021-02-04
tags: [machine learning, ComputerVision]
header:
  image: "/images/confusion_matric.jpg"
excerpt: "jupyter notebook"
mathjax: "true"
toc: true
toc_sticky: true
sidebar:
    nav: sidebar-sample    
---
In this article we will understand and apply confusion matrix on a multi-class machine learning models rather than the binary classification problem.

Basically a confusion matrix is represented in a tabular format to visualize the performance of your pediction model. Every mentry logged in the confusion matrix (table) indicates the number of predictions
made by the model where it is classified the classes correctly or incorrectly.

Remember the confusion matrix is depicted using 4 key metrics

#### **1. True Positive (TP)**: 

Defination 1: The model correctly predicted **Yes**

Defination 2: Number of predictions where the classifier correctly predicts the **positive class as positive**.


#### **2. True Negative (TN)**: 

Defination 1: The model correctly predicted **No**.

Defination 2: Number of predictions where the classifier correctly predicts the **negative class as negative**.

#### **3. False Positives (FP)**: 

Defination 1: The model **falsely** predicted **Yes**

Defination 2: The number of predictions where the classifier **incorrectly** predicts **the negative class as positive**.

#### **4. False Negatives (FN)**: 

Defination 1: The model **falsely** predicted **No**

Defination 2: "The number of predictions where the classifier **incorrectly** predicts the **positive class as negative**.

Confused... :confused:

Let me make it simple with example to understand the definations

Let's understand in detailed:

**Problem: Suppose we are working on a binary classifier to predict whether the patient is sick or healthy**. 

***Given, **positive** (the patient is sick) or **negative** (the patient is healthy)***

Let us run our classifier on 1000 patients data and enter the model predictions

|                             | Predicted sick (positive)      | Predicted healthy (negative)   |
|-----------------------------|--------------------------------|--------------------------------|
| Sick patients (positive)    | 100<br><br>True Positives (TP) | 30<br><br>False Negative (FN)  |
| Healthy patients (negative) | 70<br><br>False Positives (FP) | 800<br><br>True Negatives (TN) |


Let's sum up the values of TP, TN, FP, FN out of 1000

TP: 100

TN: 800

FP: 70

FN: 30


Now we use these measures from the confusion matrix to calculate the ML metrics such as

**1. Accuracy**

**2. Precision and Recall**

**3. F-Score**

Let's understand each metric in detail :student:	













