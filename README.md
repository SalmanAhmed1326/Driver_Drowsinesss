# Drowsiness Detection Using Facial Landmarks

This project implements a **Drowsiness Detection System** using OpenCV, dlib, and NumPy. It uses facial landmarks to monitor the eye aspect ratio (EAR) and detect if the user is **sleeping**, **drowsy**, or **active**.

---

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Dependencies](#dependencies)
- [Acknowledgments](#acknowledgments)

---

## Introduction

The system continuously monitors a live video feed from the webcam. It analyzes the position of key facial landmarks (specifically around the eyes) to compute the EAR. Based on the EAR values:
- The system detects if the user is **active**, **drowsy**, or **asleep**.
- Alerts the user with on-screen messages.

---

## Features

1. **Real-time Detection**:
   - Works with live video feed from the webcam.
2. **Eye Blink Detection**:
   - Computes the ratio of eye landmarks to detect blinking patterns.
3. **Activity Monitoring**:
   - Identifies and categorizes user activity into:
     - **Active**: User is attentive.
     - **Drowsy**: User shows signs of drowsiness.
     - **Sleeping**: User appears to be sleeping.

---

## Installation

1. Clone the repository:
   ```bash
   git clone url
   cd DrowsinessDetection
   ```

2. Install the required dependencies:
   ```bash
   pip install opencv-python numpy dlib imutils
   ```

3. Download the pre-trained [shape_predictor_68_face_landmarks.dat](https://github.com/davisking/dlib-models) file and place it in the project directory.

---

## Usage

1. Run the script:
   ```bash
   python Driver_Drowsiness.py
   ```

2. Ensure your webcam is connected. The program will start capturing the video feed and display two windows:
   - **Frame**: The real-time detection status.
   - **Result of Detector**: Detected facial landmarks.

3. Press `Esc` to exit the program.

---

## How It Works

### Key Steps:
1. **Face Detection**: Uses dlib's `frontal_face_detector` to locate the face in the video frame.
2. **Facial Landmarks Extraction**:
   - Extracts 68 landmarks using the `shape_predictor_68_face_landmarks.dat`.
   - Focuses on landmarks around the eyes for EAR calculation.
3. **Eye Blink Ratio**:
   - Calculates the EAR to detect blinking:
     - EAR > 0.25: Eyes open (Active).
     - 0.21 < EAR <= 0.25: Drowsy.
     - EAR ≤ 0.21: Eyes closed (Sleeping).
4. **Categorization**:
   - Monitors activity states over time to classify user behavior into **Active**, **Drowsy**, or **Sleeping**.

---

## Dependencies

- Python 3.x
- OpenCV
- dlib
- NumPy
- imutils

---

## Acknowledgments

- [dlib](http://dlib.net) for the pre-trained 68 facial landmarks model.
- [OpenCV](https://opencv.org/) for real-time image processing.

---

For any issues or contributions, feel free to raise an issue or submit a pull request.
