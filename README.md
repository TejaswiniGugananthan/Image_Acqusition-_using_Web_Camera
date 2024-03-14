# Image_Acqusition-_using_Web_Camera:

## Aim: 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used:
Anaconda - Python 3.7

## Algorithm

### Step 1:
Use cv2.VideoCapture(0) to access web camera

### Step 2:
Use cv2.imread to read the video or image

### Step 3:
Use cv2.imwrite to save the image

### Step 4:
Use cv2.imshow to show the video

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:

 Developed By: G.TEJASWINI
 
 Register No: 212222230157
 


### i) Write the frame as JPG file


```python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("sample.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

### ii) Display the video

```python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```


### iii) Display the video by resizing the window

```python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

### iv) Rotate and display the video

```python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image

<img width="477" alt="image" src="https://github.com/TejaswiniGugananthan/Image_Acqusition-_using_Web_Camera/assets/121222763/9ad5be3f-f575-4f90-9637-29f29c2828ed">


### ii) Display the video

<img width="479" alt="Screenshot 2024-03-14 145808" src="https://github.com/TejaswiniGugananthan/Image_Acqusition-_using_Web_Camera/assets/121222763/f58c0eca-e377-4f9d-a03a-63f972f715c5">


### iii) Display the video by resizing the window

<img width="481" alt="Screenshot 2024-03-14 145941" src="https://github.com/TejaswiniGugananthan/Image_Acqusition-_using_Web_Camera/assets/121222763/54df32a4-e518-462c-bafc-f5d7b3cd9c87">


### iv) Rotate and display the video


<img width="481" alt="Screenshot 2024-03-14 150121" src="https://github.com/TejaswiniGugananthan/Image_Acqusition-_using_Web_Camera/assets/121222763/5d6d8e92-37df-4506-8ca0-f58ea0dca9ba">




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
