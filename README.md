# EDGE LINKING USING HOUGH TRANSFORM
## AIM:
To write a Python program to detect the lines using Hough Transform.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### STEP 1:
Import all the necessary modules for the program.

### STEP 2:
Load a image using imread() from cv2 module.

### STEP 3:
Convert the image to grayscale.

### STEP 4:
Using Canny operator from cv2,detect the edges of the image.

### STEP 5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.

### STEP 6:
Display the image and end the program.

## PROGRAM:

```
NAME  : Bhavishya Reddy Mitta
REG.NO: 212221230061 
```

### READ IMAGE AND CONVERT IT TO GRAYSCALE IMAGE
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("Road.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()
```

### FIND THE EDGES IN THE IMAGE USING CANNY DETECTOR AND DISPLAY
```
edge = cv2.Canny(img,100,200)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()
```

### DETECT POINTS THAT FORM A LINE UNING HOUGHLINESP
```
lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
```

### DRAW LINES ON THE IMAGE
```
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)
```

### DISPLAY THE RESULT
```
plt.imshow(edge)
plt.axis('off')
plt.show()
```

## OUTPUT:

### INPUT IMAGE AND GRAYSCALE IMAGE

![dip 8-1](https://user-images.githubusercontent.com/94679395/234520558-de1cfe96-5208-43d8-8cf7-805a2d1f5a18.jpg)


### CANNY EDGE DETECTOR OUTPUT
![dip 8-2](https://user-images.githubusercontent.com/94679395/234520517-81664da2-1988-4d8b-9507-28892ee90032.jpg)


### DISPLAY THE RESULT OF HOUGH TRANSFORM
![dip 8-3](https://user-images.githubusercontent.com/94679395/234520472-aec260b6-226e-47f9-aec3-48976af75bc5.jpg)



## RESULT:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
