# EXP.2-Record-Image-Acquisition-using-Web-Camera
Image Capture and Video Processing Using OpenCV
## Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file
Display the video
Display the video by resizing the window
Rotate and display the video
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)

## Algorithm
Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

## Program Developed By:
# Name: N.KANISHKA

# Register Number: 212225230127

## Program:
```
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
<img width="612" height="500" alt="image" src="https://github.com/user-attachments/assets/2e0d72b4-8c1c-45a5-b211-43372c4ff94e" />
<img width="612" height="456" alt="image" src="https://github.com/user-attachments/assets/a49379c0-6b9d-4a12-868c-7d08aa601271" />
<img width="305" height="452" alt="image" src="https://github.com/user-attachments/assets/12c5fe16-90f7-4eaa-b4e2-b0e5fe8cee96" />
<img width="342" height="452" alt="image" src="https://github.com/user-attachments/assets/4b568a7c-f3d0-4f96-9a11-99ce71340786" />


## Result:
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
