# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program 
Name: Stanley S 
Reg no.212223110054
### Input image and grayscale image

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Tiger.jpg')  # Replace with your image path
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')

<img width="642" height="402" alt="image" src="https://github.com/user-attachments/assets/d831171a-1013-4fd7-8d93-c67462b3597e" />


gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

<img width="647" height="402" alt="image" src="https://github.com/user-attachments/assets/d14decc6-ccd7-4df8-98db-6425d515ddb5" />


### Canny Edge detector output

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

<Figure size 640x480 with 1 Axes><img width="515" height="321" alt="image" src="https://github.com/user-attachments/assets/0f4fb3f7-82f9-4e47-8ee6-e596a3b7a023" />



### Display the result of Hough transform

lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')


<Figure size 640x480 with 1 Axes><img width="515" height="321" alt="image" src="https://github.com/user-attachments/assets/ac46264c-dff0-43cb-a495-f9b338b9322e" />


### Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.
