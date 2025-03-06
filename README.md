Face Detection with OpenCV
This project is a simple face detection script using Python and the OpenCV library. The script captures live video from the webcam, detects faces in real-time, and draws a rectangle around each detected face.

Requirements
Python 3.x
OpenCV library (cv2)

You can install the required library with:
pip install opencv-python

How It Works
Loading the Cascade Classifier:
The script uses OpenCV’s pre-trained Haar Cascade classifier for frontal face detection:
face_cap = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_frontalface_default.xml")

Accessing the Webcam:
It opens the webcam for capturing live video:

video_cap = cv2.VideoCapture(0)

Face Detection Loop:
The script continuously reads frames from the webcam, converts them to grayscale, and detects faces:
col = cv2.cvtColor(video_data, cv2.COLOR_BGRA2GRAY)
faces = face_cap.detectMultiScale(
    col,
    scaleFactor=1.1,
    minNeighbors=5,
    minSize=(30, 30),
    flags=cv2.CASCADE_SCALE_IMAGE
)

Drawing Rectangles:
For each detected face, a green rectangle is drawn:
cv2.rectangle(video_data, (x, y), (x + w, y + h), (0, 255, 0), 2)

Displaying the Video:
The live video feed with detected faces is shown in a window named video_live.

Exiting the Program:
Press the A key to exit the live video feed and close the window:
if cv2.waitKey(10) == ord("a"):
    break

Usage
Save the script as face_detection.py.

Run the script:
python face_detection.py

Allow camera access when prompted.
A window will appear showing the live video feed with face detection.
Press the A key to exit the program.

Troubleshooting
Camera Not Opening: Ensure your webcam is properly connected.
Face Not Detected: Check for proper lighting and that your face is clearly visible to the camera.
Library Errors: Ensure OpenCV is correctly installed with pip install opencv-python.

Future Improvements
Add face recognition capabilities.
Save detected faces as image files.
Detect multiple features (eyes, smile, etc.) using other cascade classifiers.
