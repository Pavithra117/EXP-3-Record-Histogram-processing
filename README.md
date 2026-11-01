# EXP-3-Record-Histogram-processing
## NAME : PAVITHRA K
## REG.NO : 212224240112

## Aim:
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

1.Read and display a grayscale image

2.Plot histogram of the grayscale image

3.Apply histogram equalization on grayscale image

4.Read and display a color image

5.Plot histogram of B, G, R channels

6.Convert image to HSV color space

7.Apply histogram equalization on the Value (V) channel

8.Convert the enhanced image back to BGR format

9.Display original and enhanced images with histograms

## Software Used:
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## Algorithm:
Step 1: Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2: Read the image parrot.jpg in grayscale format.

Step 3: Display the grayscale image and plot its histogram.

Step 4: Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5: Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6: Read the same image in color format.

Step 7: Split the image into B, G, R channels and plot their histograms.

Step 8: Convert the image from BGR to HSV color space.

Step 9: Apply histogram equalization on the V (Value) channel.

Step 10: Merge the channels and convert the image back to BGR format.

Step 11: Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

## Program:
```
## Import Python necessary libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('pavithra image.png', cv2.IMREAD_GRAYSCALE)

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
img = cv2.imread('pavithra image.png', cv2.IMREAD_COLOR)
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
```

## Output:
 <img width="471" height="498" alt="image" src="https://github.com/user-attachments/assets/9194e947-8ef6-47e2-9a67-005d7a3eaa1c" />

 <img width="660" height="499" alt="image" src="https://github.com/user-attachments/assets/fe7b89e2-2177-4fda-a353-7429e99cf6e2" />

 <img width="726" height="508" alt="image" src="https://github.com/user-attachments/assets/0f47d960-8c42-4050-848e-fea944bcc17e" />

 <img width="509" height="500" alt="image" src="https://github.com/user-attachments/assets/9401d24f-1a25-4add-a906-4cfb5b5257b5" />

 <img width="480" height="483" alt="image" src="https://github.com/user-attachments/assets/985f0cf2-2149-4ab2-bd6f-e8f31193992b" />

 <img width="699" height="506" alt="image" src="https://github.com/user-attachments/assets/b3d6ccae-2a1d-43b3-a6e1-399f1aa18934" />

 <img width="1240" height="419" alt="image" src="https://github.com/user-attachments/assets/6158585d-e8a4-4f19-886c-699c0db19c01" />

 <img width="1244" height="368" alt="image" src="https://github.com/user-attachments/assets/cc4fed4e-f178-49f7-84cb-eb829b3bfd26" />



## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
