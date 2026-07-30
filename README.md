## Image Capture and Video Processing Using OpenCV
## Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:
1.Write the frame as a JPG file
2. Display the video
3. Display the video by resizing the window
4. Rotate and display the video
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

## Program
Developed By: Harshana M V

Register No:212224240053

## Output
i) Write the frame as JPG image
```import cv2
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
```
<img width="651" height="520" alt="image" src="https://github.com/user-attachments/assets/9b069b84-8b01-40f5-bacb-34dcf8d6c4a5" />


ii) Display the video
Live webcam video is displayed
```
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
```
<img width="640" height="486" alt="image" src="https://github.com/user-attachments/assets/8b9600ad-e7e4-442f-9ecb-e0d6226064da" />



iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```cap = cv2.VideoCapture(0)

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
```
<img width="322" height="487" alt="image" src="https://github.com/user-attachments/assets/0c5ccc7a-d9ad-48f2-8fb0-a3dac492ac0e" />


iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
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
<img width="362" height="477" alt="image" src="https://github.com/user-attachments/assets/bd661bda-7068-4216-beb7-7e1791d3410d" />


## Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.# EXP-2-Record-Image-Acquisition-using-Web-Camera
