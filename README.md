# Exp-5-Record-Implementation-of-Filters

## Developed By: NAVASRI B
## Register Number: 212225230196 

## Aim

To implement filters for smoothing and sharpening images in the spatial domain.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import the required libraries.

### Step 2
Read the image and convert it from BGR to RGB.

### Step 3
Apply the required smoothing and sharpening filters to the image separately.

### Step 4
Plot and display the original and filtered images using `matplotlib.pyplot`.

### Step 5
End the program.

## Program

## 1. Smoothing Filters

### i) Using Averaging Filter

```
python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("sv.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

### ii) Using Weighted Averaging Filter

```
python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show())
```

### iii) Using Gaussian Filter

```
python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

### iv) Using Median Filter

```
python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

## 2. Sharpening Filters

### i) Using Laplacian Linear Kernel

```
python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

### ii) Using Laplacian Operator

```
python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## Output

### 1. Smoothing Filters

#### i) Using Averaging Filter

<img width="732" height="502" alt="image" src="https://github.com/user-attachments/assets/42edef0a-5044-40b8-b529-780e3070a5e1" />



#### ii) Using Weighted Averaging Filter

<img width="587" height="350" alt="image" src="https://github.com/user-attachments/assets/48538482-a9a1-4d28-bfcc-3529add694e9" />


#### iii) Using Gaussian Filter

<img width="582" height="355" alt="image" src="https://github.com/user-attachments/assets/a5ce0be6-5144-4e01-a5da-fb04f0930028" />


#### iv) Using Median Filter

<img width="728" height="477" alt="image" src="https://github.com/user-attachments/assets/de67f4b6-a0c0-422c-bb3d-ed426cdb36ac" />


### 2. Sharpening Filters

#### i) Using Laplacian Kernel

<img width="550" height="357" alt="image" src="https://github.com/user-attachments/assets/1a2036bd-e51d-4b2c-87fb-fd845a738ab4" />


#### ii) Using Laplacian Operator

<img width="570" height="357" alt="image" src="https://github.com/user-attachments/assets/a39d25fd-9d82-418c-b8ea-c953f4abad4a" />


## Result

Thus, filters were implemented for smoothing and sharpening images in the spatial domain using OpenCV and Python.
