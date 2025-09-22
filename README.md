
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.
### Step 5:
End the program and close the output video window by pressing 'q'.
## Program:
``` Python
### Developed By:ibrahim fedah s
### Register No:212223240056

## i) Write the frame as JPG file
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()

## ii) Display the video

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


## iii) Display the video by resizing the window

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()



## iv) Rotate and display the video

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


```
## Output

### i) Write the frame as JPG image
<img width="512" height="411" alt="download" src="https://github.com/user-attachments/assets/8ef05c5d-a4a7-4790-9144-20cc6262b9b5" />





### ii) Display the video
<img width="512" height="411" alt="download" src="https://github.com/user-attachments/assets/3c684693-0eb3-46fa-9db7-a3d6b06e3a79" />



### iii) Display the video by resizing the window
<img width="266" height="389" alt="download" src="https://github.com/user-attachments/assets/088c76f7-c8a1-452f-93e8-d1eddc97f7c2" />






### iv) Rotate and display the video
<img width="266" height="389" alt="download" src="https://github.com/user-attachments/assets/5157a3f7-7de6-4f35-8bdc-48d80fd3f85a" />









## Result:
Thus the image is accessed from webcamera and displayed using openCV.
