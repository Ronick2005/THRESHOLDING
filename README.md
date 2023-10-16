# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding, and Otsu's thresholding using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image.
### Step6:
Display the results.

## Program
### Load the necessary packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### Read the Image and convert to grayscale
```python
image=cv2.imread("spiderman.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("spiderman.jpg",0)0
```
### Use Global thresholding to segment the image
```python
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```python
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```python
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```

## Output
### Original Image
![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/1f36b067-4468-4ad1-86e2-2b804fcf3480)

### Global Thresholding
![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/f797300b-5b33-40a2-b389-c06cf06cb75f)

![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/496a514c-23d3-4d5b-b068-813a19c356a3)

![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/16a5c84c-bbf7-4ac4-a247-4d89391a5a12)

![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/e460c338-86fc-482c-bac2-2367e5f468a8)

![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/df14d956-e9e0-4c91-9663-4b67aa7e85da)

### Adaptive Thresholding
![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/a7b97889-69c0-42c8-b06e-85d2315c6ad9)

![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/255d6031-ad6a-434d-931a-831fc2973842)

### Optimum Global Thresholding using Otsu's Method
![image](https://github.com/Ronick2005/THRESHOLDING/assets/83219341/d00e40d2-029f-48b3-99e6-c91e9ca32f45)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding, and optimum global thresholding using Python and OpenCV.

