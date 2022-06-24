### EX NO: 02
### DATE:
# <p align="center">EDGE LINKING USING HOUGH TRANSFORM</p>

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
## Program:
```
### Developed By   : N Sandhya Charu
### Register Number: 212220230041
```
```Python
# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image=cv2.imread("image3.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("GRAY_IMAGE",image1)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Find the edges in the image using canny detector and display

canny_edges=cv2.Canny(image1,120,150)
plt.imshow(canny_edges,cmap='gray')
plt.title('Canny Edges')
plt.xticks([])
plt.yticks([])

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(canny_edges,1,np.pi/180,threshold = 80,minLineLength=50,maxLineGap=250)

# Draw lines on the image

for line in lines:
    x1,y1,x2,y2= line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,255,0),3)

# Display the result

plt.imshow(image,cmap='gray')
plt.title('image')
plt.xticks([])
plt.yticks([])

```
## Output

### Input image and grayscale image
![WhatsApp Image 2022-05-24 at 4 10 06 PM](https://user-images.githubusercontent.com/75235167/170016884-e3f5716a-333d-4935-8b3b-b98be5e16d87.jpeg)

![WhatsApp Image 2022-05-24 at 4 13 51 PM](https://user-images.githubusercontent.com/75235167/170016552-83d0c9f4-d6e9-459f-bd2e-05abfbc98484.jpeg)

### Canny Edge detector output
![WhatsApp Image 2022-05-24 at 4 13 00 PM](https://user-images.githubusercontent.com/75235167/170016215-739b4ca2-e7af-4c9d-96ee-386b657c7b0c.jpeg)

### Display the result of Hough transform
![WhatsApp Image 2022-05-24 at 4 12 24 PM](https://user-images.githubusercontent.com/75235167/170015963-ad24624a-bbad-40d6-839f-064f5e33f9ca.jpeg)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
