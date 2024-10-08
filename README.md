# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the image

### Step2:
Convert the input image to gray to get more details

### Step3:
Apply any smoothing filter, here we apply Gaussian blur

### Step4:
Apply an edge detector

### Step5:
Apply hough transform and show the detected edge on the original image


## Program:

```
Developed By : GANJI MUNI MADHURI
Register Number : 212223230060
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Fish.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.figure(figsize=(12, 12))

# Input Image and Grayscale Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

# Canny Edge Detection Output
plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')

# Hough Transform Result
plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')

# Display all results
plt.show()
```




## Output

![image](https://github.com/user-attachments/assets/9b769e4c-c4c0-4922-9f94-c6565a9a98b2)
![image](https://github.com/user-attachments/assets/60989b5e-f0af-4590-95f9-4449cc65c8cd)
![image](https://github.com/user-attachments/assets/3aa5e7f5-fcdb-4c0b-8ec1-ae0224f4e774)
![image](https://github.com/user-attachments/assets/e9acd691-2baa-4538-8eb3-1cfc9cb8f32e)





## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform. 
