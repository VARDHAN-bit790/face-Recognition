# Face Recognition Attendance System
## Overview

This is a Face Recognition Attendance System that uses the OpenCV and face_recognition libraries to recognize faces from a webcam feed and mark attendance. The system will compare detected faces with the training images in the `Training_images` folder and log recognized faces along with their timestamps in an `Attendance.csv` file.

## Features

- Real-time face detection using the webcam.
- Compares detected faces with pre-trained images.
- Marks attendance for recognized faces in the `Attendance.csv` file.
- Creates bounding boxes around detected faces and displays the name below them.

## Installation

### Prerequisites

Before running the system, you need to have Python 3.x installed on your system.

### Libraries

To install the necessary Python libraries, use the following commands:

1. **OpenCV**:
   OpenCV is used for image processing and video capture.

   ```bash
   pip install opencv-python
NumPy: NumPy is used for numerical operations like distance calculations.

bash
Copy
pip install numpy
face_recognition: The face_recognition library is used to detect faces and compare them with known encodings.

bash
Copy
pip install face_recognition
dlib (dependency for face_recognition): In case you face any issues installing face_recognition, install dlib first.

bash
Copy
pip install dlib
pip install face_recognition
Optional: Full OpenCV functionality:

bash
Copy
pip install opencv-contrib-python
Setup
Create a folder named Training_images in the project directory.

Place images of the people to be recognized in the folder.
The images should be in .jpg or .png format.
The filename should represent the person's name (e.g., John_Doe.jpg).
Create the Attendance CSV file.

The system will write attendance data to an Attendance.csv file.
The file should be created in the project directory with the following format:
pgsql
Copy
name,time
Usage
Ensure that you have the required images in the Training_images folder.

Run the script using the following command:

bash
Copy
python your_script_name.py
The program will open the webcam and start recognizing faces. If a face is recognized, the system will:

Draw a bounding box around the face.
Display the name of the recognized person.
Log the name and timestamp in the Attendance.csv file.
Press q to quit the program and stop the webcam feed.

Example
The program will open the webcam feed and display a window showing the video.
If a person’s face is detected and matches any face in the Training_images folder, it will display the person's name under the bounding box.
If the person is recognized, their name and the timestamp of when they were recognized will be logged in the Attendance.csv file.
Code Walkthrough
Image Loading and Encoding:

The script loads images from the Training_images folder and computes their face encodings.
These encodings are stored in knownEncodings for later comparison.
Face Detection in Real-time:

The webcam feed is continuously captured frame by frame.
Each frame is processed to detect faces and compute their encodings.
Face Recognition:

For each detected face, the script compares the encoding with the known encodings.
If a match is found, the person's name is displayed and attendance is recorded.
Logging Attendance:

The Attendance.csv file stores the name and time of the recognized person.
Attendance is logged only if the person is not already recorded for that session.
Files
Training_images: Folder containing the training images of people for recognition.
Attendance.csv: File where attendance will be logged.
your_script_name.py: Python script that runs the face recognition system.
Troubleshooting
Issue with dlib installation:

If you encounter issues installing dlib, you can download precompiled dlib wheels from here for Windows users.
Face not detected:

Make sure the person is facing the camera clearly.
Ensure there is enough lighting for proper face detection.
Attendance not being recorded:

Make sure the person’s name is correctly stored in the Training_images folder.
Ensure the Attendance.csv file exists and is not locked or being used by another application.
