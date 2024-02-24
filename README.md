# Image_Acqusition-_using_Web_Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:
``` Python
### Developed By: Athmaj Venugopal
### Register No: 212222240014
```

## i) Write the frame as JPG file
```Python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("Athmaj.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Athmaj',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222240014-Athmaj',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222240014-Athmaj',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![Screenshot 2024-02-24 214114](https://github.com/ATHMAJ03/Image_Acqusition-_using_Web_Camera/assets/118753139/b9f35688-8120-4acc-b5ca-abfb097bcefe)


### ii) Display the video

![Screenshot 2024-02-24 212158](https://github.com/ATHMAJ03/Image_Acqusition-_using_Web_Camera/assets/118753139/b9ea3980-3b2c-4b43-a9d5-14bd036d6038)


### iii) Display the video by resizing the window
![Screenshot 2024-02-24 214712](https://github.com/ATHMAJ03/Image_Acqusition-_using_Web_Camera/assets/118753139/61718f81-113e-480a-a36d-73bae1747d41)


### iv) Rotate and display the video

![Screenshot 2024-02-24 214952](https://github.com/ATHMAJ03/Image_Acqusition-_using_Web_Camera/assets/118753139/2de789c4-4e54-4f2b-821c-d52c8d972276)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.


