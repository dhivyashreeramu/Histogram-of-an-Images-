# Ex.No: 03 Histogram of an Images
# Name: DHIVYASHREE R
# Reg. No: 212225040077

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the cv2.imread() function.

### Step 2
Display the grayscale and color images using the imshow() function.

### Step 3
Use the cv2.calcHist() function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the cv2.calcHist() function to calculate the histograms of the Blue, Green, and Red channels of the color image.
### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('me.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')


## Output

### Input Grayscale Image

<img width="273" height="434" alt="image" src="https://github.com/user-attachments/assets/17a5e8c6-97c1-4721-941c-6e0c1bba97e0" />


### Input Grayscale Image Range
<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/cdce7372-5bf1-41bc-ba17-3f2bded0a319" />


### Input Grayscale Image Equalized Histogram
<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/ecee6a3c-5dd0-4c07-b1d2-c6156db3702e" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="273" height="434" alt="image" src="https://github.com/user-attachments/assets/619ae338-1f80-47d3-a67d-e6d96f3d8dcf" />

### Equalized Image

<img width="273" height="434" alt="image" src="https://github.com/user-attachments/assets/98f2b3d8-cc33-4cbc-b24a-e6dd80f2f345" />


### Equalized Histogram
<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/7ac841cd-2dad-46af-bfc4-1a8eee9c6b4d" />


### Final Output of Original Image and Equalized 
<img width="1107" height="414" alt="image" src="https://github.com/user-attachments/assets/92d376b5-c435-4b0e-8fc7-08a4b0178d6a" />



### Final Output of Original Image and its Histogram Equalized
<img width="1237" height="372" alt="image" src="https://github.com/user-attachments/assets/c4006ab9-cf54-4ede-aab0-a9eb08aaae95" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
