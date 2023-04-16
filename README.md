# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1

Import libraries and read the saved images using cv2.imread().

### Step2

Convert the saved BGR image to RGB using cvtColor().

### Step3

By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4

Apply the filters using cv2.filter2D() for each respective filters.

### Step5

Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().
## Program:
```Python
# Developed By   : A Naveen Kumar
# Register Number: 212221240032
```
</br>

# 1. Smoothing Filters
```Python

import cv2
import matplotlib.pyplot as plt
import numpy as np
#i) Using Averaging Filter

image1=cv2.imread("image.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/121

avg_filter = cv2.filter2D(image2,-1,kernel)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")


#ii) Using Weighted Averaging Filter

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(image1,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image1)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")

#iii) Using Gaussian Filter

gaussian_blur = cv2.GaussianBlur(src = image1, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image1)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")


#iv) Using Median Filter

median = cv2.medianBlur(src=image1,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image1)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")
```


# 2. Sharpening Filters
```python
#i) Using Laplacian Kernal

kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(image1,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image1)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")

#ii) Using Laplacian Operator

laplacian_operator = cv2.Laplacian(image1,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image1)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")
```

## OUTPUT:
### 1. Smoothing Filters
i) Using Averaging Filter

![img1](https://user-images.githubusercontent.com/94387019/232283403-45bf2d63-db00-49e7-9c42-8d51a64273ed.jpg)


ii) Using Weighted Averaging Filter

![img2](https://user-images.githubusercontent.com/94387019/232283411-2253e29c-d943-41c7-a670-5b7b677c7351.jpg)


iii) Using Gaussian Filter

![img3](https://user-images.githubusercontent.com/94387019/232283419-2f06909f-e0bf-4962-b93a-a800276b594c.jpg)


iv) Using Median Filter

![img4](https://user-images.githubusercontent.com/94387019/232283435-a0623e20-bd00-4921-b2e3-e1af54093783.jpg)


### 2. Sharpening Filters
i) Using Laplacian Kernal

![img5](https://user-images.githubusercontent.com/94387019/232283448-957840c5-4462-4ccd-9af2-92b55ad6ed14.jpg)


ii) Using Laplacian Operator

![img6](https://user-images.githubusercontent.com/94387019/232283559-4272e345-7de1-430a-8ae3-d7e4a40bd02c.jpg)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
