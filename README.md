# Hand Gesture Volume Control

This project uses computer vision and hand gesture recognition to control the system volume. By detecting the distance between the thumb and index finger using a webcam, the system volume is adjusted accordingly. The project uses OpenCV for video processing, MediaPipe for hand tracking, and PyCaw for controlling the audio volume on Windows.

## Features
- Real-time hand gesture recognition using a webcam.
- Adjust system volume based on the distance between thumb and index finger.
- Visual feedback for hand detection and volume level.

## Requirements
- Python 3.6+
- OpenCV
- MediaPipe
- NumPy
- PyCaw
- Comtypes

## Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/yourusername/hand-gesture-volume-control.git
    cd hand-gesture-volume-control
    ```

2. **Install dependencies:**
    ```sh
    pip install opencv-python mediapipe numpy pycaw comtypes
    ```

## Usage

1. **Run the main script:**
    ```sh
    python main.py
    ```

2. **Using the application:**
    - Ensure your webcam is connected.
    - The script will open a window showing the webcam feed.
    - Show your hand in front of the camera with the palm facing the camera.
    - The system will detect your hand and show landmarks on your thumb and index finger.
    - Adjust the distance between your thumb and index finger to control the system volume.

## How It Works

1. **Hand Detection:**
    - The `handDetector` class in `handtrackingmin.py` uses MediaPipe to detect hand landmarks.
    - The `findHands` method processes the webcam feed and detects hands.
    - The `findPosition` method extracts the coordinates of specific landmarks (e.g., thumb and index finger).

2. **Volume Control:**
    - The `main.py` script captures the webcam feed and uses the `handDetector` to find hand landmarks.
    - The distance between the thumb and index finger is calculated.
    - The volume level is adjusted based on this distance using PyCaw.

3. **Visual Feedback:**
    - Circles and lines are drawn on the detected landmarks for visual feedback.
    - A volume bar is displayed to indicate the current volume level.
    - FPS (frames per second) is displayed on the video feed.

## Code Structure

- `main.py`: Main script for running the hand gesture volume control.
- `handtrackingmin.py`: Contains the `handDetector` class for hand detection and landmark extraction.

## References

- [OpenCV Documentation](https://docs.opencv.org/)
- [MediaPipe Documentation](https://mediapipe.dev/)
- [PyCaw Documentation](https://github.com/AndreMiras/pycaw)
