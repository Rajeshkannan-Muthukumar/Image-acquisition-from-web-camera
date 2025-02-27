# Image-Acquisition-from-Web-Camera
## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.


    i) Write the frame as JPG 
    ii) Display the video 
    iii) Display the video by resizing the window
    iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7 , JUPYTER NOTEBOOK
## Algorithm
### Step 1:

Import Opencv Package.

### Step 2:

Capture the Video from the WebCamera.

### Step 3:

Write the image to a file.


### Step 4:

Show the image or the live camera.


### Step 5:

End the program.


## Program:
         Developed By: M.RAJESHKANNAN
         Register No: 212221230081

## i) Write the frame as JPG file

```
import cv2
video = cv2.VideoCapture(0)
while (True):
    cap,frame=video.read()
    cv2.imwrite('video.jpeg',frame) 
    result = False
video.release()
cv2.destroyAllWindows()

```


## ii) Display the video

```
import cv2
video = cv2.VideoCapture(0)
while (True):
    cap,frame=video.read()
    cv2.imshow('Capturing Video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
video.release()
cv2.destroyAllWindows()

```


## iii) Display the video by resizing the window

```
import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=small_frame
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=small_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
video.release()
cv2.destroyAllWindows()
    

```



## iv) Rotate and display the video

```
import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
video.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![Output](video.jpeg)

### ii) Display the video

![Output](OP1.png)

### iii) Display the video by resizing the window
![Output](OP2.png)

### iv) Rotate and display the video

![Output](OP3.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
