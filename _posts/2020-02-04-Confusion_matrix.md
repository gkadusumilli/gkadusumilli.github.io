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
Anyone familiar with the confusion matrix knows that most of the time it is explained for a binary classification problem. Well, in this article we will extend applying confusion matrix on multi-class machine learning models.

A confusion matrix is represented in a tabular format to visualize the performance of our prediction model. Every entry logged in the confusion matrix (table) indicates the number of predictions made by the model where it classified the classes correctly or incorrectly.

# Confusion matrix for Binary Classification

The confusion matrix table mainly consists of 4 entries they are:

### **1. True Positive (TP)**: 

Definition 1: The model correctly predicted **Yes**

Definition 2: Number of predictions where the classifier correctly predicts the **positive class as positive**.


### **2. True Negative (TN)**: 

Definition 1: The model correctly predicted **No**.

Definition 2: Number of predictions where the classifier correctly predicts the **negative class as negative**.

### **3. False Positives (FP)**: 

Defination 1: The model **falsely** predicted **Yes**

Definition 2: The number of predictions where the classifier **incorrectly** predicts **the negative class as positive**.

### **4. False Negatives (FN)**: 

Defination 1: The model **falsely** predicted **No**

Definition 2: "The number of predictions where the classifier **incorrectly** predicts the **positive class as negative**.

Confused... :confused:

Let me make it simple with an example to understand 

**Problem: Suppose we are working on a binary classifier to predict whether the patient is sick or healthy**. 

***Given, **positive** (the patient is sick) or **negative** (the patient is healthy)***

Let us run our classifier on 1000 patient's data and enter the model predictions.

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

Let's understand each metric detail :student:	

### 1. Accuracy

The accuracy metric gives the overall accuracy of the model, meaning the fraction of the total samples that were correctly classified by the classifier.

Accuracy is calculated as:

<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{TP&space;&plus;&space;TN}{TP&space;&plus;&space;TN&space;&plus;&space;FP&space;&plus;&space;FN}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{TP&space;&plus;&space;TN}{TP&space;&plus;&space;TN&space;&plus;&space;FP&space;&plus;&space;FN}" title="\frac{TP + TN}{TP + TN + FP + FN}" /></a>

### 2. Precision and Recall

**Recall** (*also known as sensitivity*) tells us how many times did the model has ***incorrectly*** classified as negative class (FN).

Recall is calculated as:

<a href="https://www.codecogs.com/eqnedit.php?latex=Recall&space;=&space;\frac{TP}{TP&space;&plus;&space;FP}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Recall&space;=&space;\frac{TP}{TP&space;&plus;&space;FP}" title="Recall = \frac{TP}{TP + FP}" /></a>

**Precision** (*also known as specificity*) is the opposite of recall. It tells us how many times did the model ***incorrectly*** diagnose as a positive class (FP)

<a href="https://www.codecogs.com/eqnedit.php?latex=Precision&space;=&space;\frac{TP}{TP&space;&plus;&space;FP}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Precision&space;=&space;\frac{TP}{TP&space;&plus;&space;FP}" title="Precision = \frac{TP}{TP + FP}" /></a>

**F-score**
In many cases, we want to summarise the performance of a classifier with a single metric that represents both recall and precision. To do so, we can convert **precision (p)** and **recall (r)** into a single F-score metric. mathematically, this is called the **harmonic mean** of ***p*** and ***r***

<a href="https://www.codecogs.com/eqnedit.php?latex=F-score&space;=&space;\frac{2pr}{p&space;&plus;&space;r}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F-score&space;=&space;\frac{2pr}{p&space;&plus;&space;r}" title="F-score = \frac{2pr}{p + r}" /></a>


# Confusion matrix for Multi-class classification

Let's consider our multi-class classification problem to be a 3-class classification problem. suppose we have a three-class label, namely **Cat**, **Dog**, and **Rat**. The following is a possible confusion matrix for these classes.

|     | Dog | Cat | Rat |
|-----|-----|-----|-----|
| Dog | 20  | 6   | 8   |
| Cat | 1   | 15  | 3   |
| Rat | 8   | 4   | 26  |

Unlike binary classification, there are no positive or negative classes here. Instead, we have TP, TN, FP, and FN for each class.

Let's calculate the accuracy of class Dog, let us see the values from the confusion matrix.

![Class Dog](/images/Dog_class.png)

* TP = 20

* TN = (15 + 3 + 4 + 26) = 48

* FP = (6 + 8) = 14

* FN = (1 + 8) = 9

Calculating metrics for class dog

* <a href="https://www.codecogs.com/eqnedit.php?latex=Precision&space;=&space;\frac{20}{20&space;&plus;&space;14}&space;=&space;58.8%" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Precision&space;=&space;\frac{20}{20&space;&plus;&space;14}&space;=&space;58.8%" title="Precision = \frac{20}{20 + 14} = 58.8%" /></a>

* <a href="https://www.codecogs.com/eqnedit.php?latex=Recall&space;=&space;\frac{20}{20&space;&plus;&space;9}&space;=&space;68.96%" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Recall&space;=&space;\frac{20}{20&space;&plus;&space;9}&space;=&space;68.96%" title="Recall = \frac{20}{20 + 9} = 68.96%" /></a>

* <a href="https://www.codecogs.com/eqnedit.php?latex=F-Score&space;=&space;\frac{2&space;*&space;58.8}{58.8&space;&plus;&space;68.96}&space;=&space;92.04" target="_blank"><img src="https://latex.codecogs.com/gif.latex?F-Score&space;=&space;\frac{2&space;*&space;58.8}{58.8&space;&plus;&space;68.96}&space;=&space;92.04" title="F-Score = \frac{2 * 58.8}{58.8 + 68.96} = 92.04" /></a>

Similarly, let's calculate the accuracy of Class Cat, let us see the values from the confusion matrix

![Class Cat](/images/Cat_class.png)
