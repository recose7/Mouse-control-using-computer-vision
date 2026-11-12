# 👁️ Mouse control Using Computer Vision

An AI-powered mouse control system that allows users to control their computer cursor using eye movements and perform mouse clicks through blinking. The project uses real-time facial landmark detection to track iris movements and detect eye closure through a webcam.

## 🚀 Project Overview

Traditional computer mice require physical interaction. This project explores an alternative human-computer interaction approach using computer vision.

By leveraging MediaPipe Face Mesh and OpenCV, the system detects facial landmarks, tracks iris position, and maps eye movements to screen coordinates. It also detects blinking by measuring the distance between upper and lower eyelid landmarks, triggering a mouse click when the eye closes.

## ✨ Features

- **Real-Time Eye Tracking:** Tracks iris landmarks using MediaPipe Face Mesh.
- **Cursor Movement:** Maps iris coordinates to screen coordinates to control the mouse pointer.
- **Blink Detection:** Detects eye closure using Euclidean distance between eyelid landmarks.
- **Mouse Click Automation:** Triggers a left mouse click when the eye is detected as closed.
- **Live Visualization:** Displays facial and eye landmarks on the webcam feed.
- **Real-Time Processing:** Continuously processes webcam frames for interactive control.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| OpenCV | Webcam access and image processing |
| MediaPipe | Facial landmark and iris detection |
| PyAutoGUI | Mouse movement and click automation |
| Math | Euclidean distance calculation |

## 🧠 Working Architecture

The system follows the pipeline below:

1. **Video Capture:** OpenCV captures real-time frames from the webcam.
2. **Image Preprocessing:** Frames are horizontally flipped and converted from BGR to RGB.
3. **Facial Landmark Detection:** MediaPipe Face Mesh detects facial landmarks with refined eye and iris landmarks enabled.
4. **Iris Tracking:** Selected iris landmarks are extracted to estimate eye position.
5. **Coordinate Mapping:** Normalized iris coordinates are mapped to screen coordinates.
6. **Cursor Control:** PyAutoGUI moves the mouse pointer according to the detected iris position.
7. **Blink Detection:** The Euclidean distance between upper and lower eyelid landmarks is calculated.
8. **Click Execution:** If the distance falls below a predefined threshold, a left mouse click is triggered.

