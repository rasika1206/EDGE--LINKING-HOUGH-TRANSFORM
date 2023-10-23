# EDGE--LINKING-HOUGH-TRANSFORM
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
Using the Canny operator from cv2, detect the edges of the images.

### Step5:
Using the houghlinesP(), detect the line co-ordinates for every points in the images. Using for loop, draw the lines on the found co-ordinates. Display the image.

## Program:


# Read image and convert it to grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('dolphin.jpg',0)
plt.imshow(image1)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)
```


# Find the edges in the image using canny detector and display
```
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()
```


# Detect points that form a line using HoughLinesP
```

lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
```


# Draw lines on the image
```
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255,0,0),3)
```


# Display the result
```
plt.imshow(edges1)
```
## Output

### Input image and grayscale image
![Screenshot from 2023-10-23 10-52-00](https://github.com/rasika1206/EDGE--LINKING-HOUGH-TRANSFORM/assets/124434806/89479ea9-244d-4973-a723-747244dcead8)

<br>
<br>
<br>
<br>

### Canny Edge detector output
![Screenshot from 2023-10-23 10-52-07](https://github.com/rasika1206/EDGE--LINKING-HOUGH-TRANSFORM/assets/124434806/f89ef1ab-3a28-4bd4-9105-e4b056746c87)

<br>
<br>
<br>
<br>


### Display the result of Hough transform
![Screenshot from 2023-10-23 10-52-15](https://github.com/rasika1206/EDGE--LINKING-HOUGH-TRANSFORM/assets/124434806/38639f1e-6c7f-4c69-a956-94783acc9524)

<br>
<br>
<br>
<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
