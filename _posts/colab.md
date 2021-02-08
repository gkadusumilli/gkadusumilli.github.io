---
title: "G Colab"
date: 2021-02-04
tags: [machine learning, ComputerVision]
header:
  image: "/images/confusion_matric.jpg"
excerpt: "Confusion matrix, Machine learning mebtrics"
mathjax: "true"
toc: true
toc_sticky: true
sidebar:
    nav: sidebar-sample    

---

**URL**: https://colab.research.google.com/ 

**Colab H/W specifications**:

**Advantages of using Colab?**

1. Free GPU !!! (One of the main reason I believe for thriving the DL community is **Open-source** and **Access to GPU's***

2. Sharing: We can share the notebooks easily with others having a Gmail account. We can also share the notebook URL for public access.

3. Github: we can **clone the git repos** with a single command and save the notebooks with hassle-free UI.

4. File downloads: In ML / DL, Datasets are crucial and, we know the file sizes are more for vision-related datasets. With moderate internet connectivity need ages to download but, with the colab, we can download in minutes (you heard right)

5. Code snippets: Colab has tiny code snippets, You can explore these on your own

6. Default pre-loaded python packages: Colab notebook is pre-installed with the libraries (up to date) for DL/ML 

***A little caution***

1. If we close the tab or lost the internet connection for more than 90 minutes, all the work will loose and, a new VM instance will be assigned.

2. Colab will remove the running VM after 12 hours, no matter how much time remained to complete the training.

### Know allocated specs

**Knowing the allocated GPU VM instance specs**

Google colab has two different GPU models, namely K80 and T4. However, we cannot select which of them you want due to the availability issues.


```python
!nvidia-smi
```

**Know the CPU and RAM info**


```python
!cat /proc/cpuinfo
!cat /proc/meminfo
```

### Setting up the libraries

**1. command to check the installed packages**


```python
!pip list 
```

**2. Package installation**

Colab comes with the pre-installed packages, if you feel the need of other packages you're free to install 


```python
#Option-1: Using pip command

!pip install opencv-contrib-python

#Option-2: using apt-get command

!apt-get -qq install -y graphviz && pip install -q pydot

```

**3. Command to check the specific package version**


```python
import keras

keras.__version__
```

### Upload / Download the Files/datasets

1. Upload files from the local directory
To upload data from the local machine
Run the below cell (To run the cell use, (shift+enter).
Click on Choose Files, local machine file directory window pops up, and then choose the file (image/video/document/ .etc) your need to upload.


```python
from google.colab import files

files.upload()
```

**2. Download from the Google drive**

Data can be downloaded from our own Gdrive or we can also download drive files shared by others (public link)

Let's get started 

1. Access the data from our Gdrive



```python
from google.colab import drive

drive.mount('/content/gdrive')
```

>2. Accessing Gdrive files shared in public

> Example: 
1. You'll fing the drive URL something similar shared below 
>>https://drive.google.com/open?id=0B_URf9ZWjSC11Xzc4R2d0N2c

2. Then copy the alpha numeric characters **after** ?id =





```python
!gdown --id 0B_URf9ZWjAW7SC11Xzc4R2d0N2c
```

**3. Downloading Files from the website**

To download the files from the website then we use **!wget** command


```python
!wget http://yann.lecun.com/exdb/mnist/train-images-idx3-ubyte.gz
```

### Zip/Unzip, untar the folders


**1. Zip the folder**

Syntax
!zip (zip file name.zip) (source folder to zip)


```python
!zip data.zip /content/sample_data 
```

**2. Unzip the folder**

syntax: 

!unzip (path to the zip folder) -d (destination folder)


```python
!unzip data.zip -d /content
```

**3. Extract tar files**



```python
!tar -xvf  '/content/train-images-idx3-ubyte'
```

### Copy / Move files



```python
# To list files within the directory 
# !ls with the folder path

!ls /content/content/
```


```python
#To copy files !cp <source file> <destination file>
!cp /content/data.zip /content/content
```


```python
# command to move files
!mv '/content/data.zip' '/content/content/sample_data'
```

### Delete a file/folder

To delete a file, *!rm* command is used 


```python
!rm '/content/Trolling Euclid.pdf'
```

To delete a folder, *!rm -rf* command is used


```python
!rm -rf /content/check
```

### Downloading datasets from Kaggle API

1. Go to your account, Scroll to API section and Click Expire API Token to remove previous tokens

2. Click on Create New API Token - It will download kaggle.json file on your machine.

3. Go to your Google Colab project file and run the following commands:



```python
! pip install -q kaggle
```


```python
#upload the kaggle.json file that you downloaded by following the above steps
from google.colab import files

files.upload()
```


```python
! mkdir ~/.kaggle
```


```python
#Make directory named kaggle and copy kaggle.json file there.
! cp kaggle.json ~/.kaggle/
```


```python
#change the permission of the file
! chmod 600 ~/.kaggle/kaggle.json
```


```python
! kaggle datasets list
```


```python
! kaggle datasets download -d emmarex/plantdisease
```


```python
!unzip /content/plantdisease.zip
```

### Cloning Git repo


```python
#To clone the git repos we use !git clone repo

!git clone https://github.com/tensorflow/models.git
```

### Running .py files


```python
!py /content/loader.py
```

### Changing working directories




```python
#to know present working directory
!pwd
```


```python
#Commands to find sub directories
!ls /content/sample_data
```

### Running Tensorboard within colab


```python
%load_ext tensorboard
%tensorboard --logdir logs
```

### Switching between tensorflow versions

Colab is pre loaded tensorflow 2.x.

If your code works with tensorflow 1.x then we can choose 1.x version using the below command


```python
%tensorflow_version 1.x
```

### Playing Video inline


```python
from IPython.display import HTML
from base64 import b64encode
mp4 = open('/content/snake_bot.mp4','rb').read()
data_url = "data:video/mp4;base64," + b64encode(mp4).decode()
HTML("""
<video width=400 controls>
      <source src="%s" type="video/mp4">
</video>
""" % data_url)
```

Thanks for going through the post

If I have missed mentioning any commands please do let me know in the comments.
