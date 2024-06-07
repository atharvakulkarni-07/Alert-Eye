# Alert-Eye: Driver Drowsiness Detection System

Alert-Eye is a real-time driver drowsiness detection system built using Python, OpenCV, and Dlib. This system continuously monitors the driver's eye movements and sounds an alarm if it detects signs of drowsiness, helping to prevent accidents caused by driver fatigue.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Dependencies](#dependencies)

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/alert-eye.git
    cd alert-eye
    ```

2. **Install the required libraries:**
    You can install the required libraries using pip:
    ```bash
    pip install -r requirements.txt
    ```

3. **Download the necessary model files:**
    - Download the `shape_predictor_68_face_landmarks.dat` from [dlib's model zoo](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2) and place it in the project directory.

4. **Set up the alarm sound:**
    - Ensure you have an alarm sound file (e.g., `alarm.wav`) in the project directory.

## Usage

1. **Run the detection script:**
    ```bash
    jupyter notebook eye_detect.ipynb
    ```
2. **Start the webcam:**
    The system will automatically start the webcam and begin monitoring for drowsiness.

3. **Alerts:**
    If the system detects that your eye aspect ratio is below the threshold for a certain number of frames, it will trigger an audible alarm to alert you.

## How It Works

The drowsiness detection system works as follows:

1. **Eye Aspect Ratio (EAR):**
    - The system calculates the Eye Aspect Ratio (EAR) to determine if the eyes are closed.
    - EAR is calculated using the distances between the vertical eye landmarks and the horizontal eye landmarks.
    - If the EAR falls below a predefined threshold, it indicates that the eyes are closed.

2. **Detection and Prediction:**
    - The system uses Dlib's frontal face detector to detect faces in the webcam feed.
    - It then uses a shape predictor to identify the landmarks of the eyes.

3. **Alarm Trigger:**
    - If the EAR is below the threshold for a continuous sequence of frames (indicating drowsiness), the system plays an alarm sound to alert the driver.

## Dependencies

- Python 3.x
- OpenCV
- Dlib
- Scipy
- Imutils
- Pygame (for playing the alarm sound)

You can install these dependencies using pip:
```bash
pip install opencv-python dlib scipy imutils pygame
```
