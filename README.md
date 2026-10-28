# DIPT_EXP_3
# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim:

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used:

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm:

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---


## Developed By:
- *Name:* POOJA PRIYA B
- *Register Number:* 212224230196

## Program:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('parrot.jpg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```
```python
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
```
```python
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
##  Output:

### ORIGINAL IMAGE:
<img width="731" height="503" alt="image" src="https://github.com/user-attachments/assets/4fa26338-8150-4d65-89bd-9539475776da" />


<img width="830" height="498" alt="image" src="https://github.com/user-attachments/assets/3d832526-3fc0-4e65-96f0-f6672e91e3c3" />


### Equalised Histogram:

<img width="785" height="535" alt="image" src="https://github.com/user-attachments/assets/dbd06234-ff3d-4dc7-aa91-ffdf735d2bdd" />


<img width="703" height="493" alt="image" src="https://github.com/user-attachments/assets/0f67aa11-cfd6-4dcf-a9ff-74f6b2c54b02" />


### Histogram of any channel of Color Image:
<img width="730" height="380" alt="image" src="https://github.com/user-attachments/assets/83ff7355-a6a0-455b-bca7-12b917cea960" />

### Histogram Equalization of Color Image:
<img width="967" height="402" alt="image" src="https://github.com/user-attachments/assets/699fdbb3-0497-457b-a872-9fdbaefaae6e" />




## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
