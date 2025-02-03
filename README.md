# Pose Detection Using OpenCV and MediaPipe

This project utilizes **OpenCV** and **MediaPipe** to detect and track hand and pose landmarks in real-time using a webcam. It identifies finger positions and body landmarks to analyze hand gestures and body posture.

## Features
- Real-time hand detection and pose estimation using MediaPipe.
- Finger tracking to detect which fingers are open or closed.
- Pose detection with landmark identification and angle calculation.
- FPS (Frames Per Second) display for performance monitoring.

## Requirements

Before running the scripts, ensure you have the following dependencies installed:

```bash
pip install opencv-python mediapipe
```

**Note:** This project is compatible with **MediaPipe version 0.8.10** and above. Ensure your Python version is **3.7** or later.

## File Structure

- `hand_detection.py`: The main script for detecting hands and identifying finger positions.
- `pose_detection.py`: The main script for detecting body poses and calculating joint angles.
- `README.md`: This file containing instructions and details about the project.

### Hand Detection
- **handDetector Class:**
  - `findHands(img, draw=True)`: Detects hands in the frame and optionally draws landmarks.
  - `findPosition(img, handNo=0)`: Returns a list of landmark positions for the specified hand.
  - `getFingers(img, handNo=0)`: Determines which fingers are open or closed.
  - `distance(point1, point2)`: Calculates the squared distance between two landmarks.

- **Main Function:**
  - Captures video from the webcam.
  - Detects hand landmarks in real-time.
  - Prints the status of each finger (open/closed) to the console.
  - Displays the FPS on the video feed.

### Pose Detection
- **PoseDetector Class:**
  - `find_pose(img, draw=True)`: Detects body poses and optionally draws landmarks.
  - `find_position(img, draw=True)`: Returns a list of body landmark positions.
  - `find_angle(img, p1, p2, p3, draw=True)`: Calculates the angle between three landmarks.

- **Main Function:**
  - Captures video from the webcam.
  - Detects body landmarks in real-time.
  - Prints landmark coordinates to the console.
  - Displays joint angles and FPS on the video feed.

## Example Output

- **Hand Detection Console Output:**
  ```
  [1, 0, 1, 1, 0]  # Thumb and pinky closed, other fingers open
  ```

- **Pose Detection Console Output:**
  ```
  [14, 320, 240]  # Coordinates of the right elbow
  ```

- FPS displayed on the video feed.

## Troubleshooting

- **Webcam Not Opening:**
  - Ensure your webcam is connected properly.
  - Check if another application is using the webcam.

- **Low FPS:**
  - Try reducing the resolution of the video capture for better performance.
  - Ensure your system meets the necessary hardware requirements.

## License

This project is licensed under the MIT License.

---

Feel free to contribute to this project by opening issues or submitting pull requests!
