# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().
### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: AHALYA S
# Register Number:212223230006 


import cv2
import numpy as np
import matplotlib.pyplot as plt
grayscale_image = cv2.imread("map.png", cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("flower.jpg")
if grayscale_image is None or color_img is None:
    print("Error: Image could not be loaded.")
    exit()
gray_hist = cv2.calcHist([grayscale_image], [0], None, [256], [0, 256])
hist_b = cv2.calcHist([color_img], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_img], [2], None, [256], [0, 256])
plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.imshow(grayscale_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')
plt.show()
plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.plot(gray_hist, color='black')
plt.title("Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Count")
plt.subplot(1, 2, 2)
plt.plot(hist_r, color='red')
plt.plot(hist_g, color='green')
plt.plot(hist_b, color='blue')
plt.title("Color Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Count")
plt.show()
plt.subplot(2, 2, 4)
plt.plot(hist_equalized, color='black')
plt.title('Equalized Histogram')
plt.xlim([0, 256])
plt.tight_layout()
plt.show()

```
## Output:
### Input Grayscale Image and Color Image

<img width="950" height="349" alt="download" src="https://github.com/user-attachments/assets/71e71543-5a96-4bcd-997a-dec49d49f34f" />

### Histogram of Grayscale Image and any channel of Color Image

<img width="1014" height="470" alt="download" src="https://github.com/user-attachments/assets/e6ec3e53-c3da-4f8b-ad56-5ecb2476fadc" />


### Histogram Equalization of Grayscale Image.
<img width="346" height="260" alt="image" src="https://github.com/user-attachments/assets/a6cefbf0-cb93-4098-a2a9-3de62e2f5208" />




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
