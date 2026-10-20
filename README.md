# Hand Volume Control

A small Python desktop app that uses a webcam and hand tracking to control system volume with a pinch gesture. It tracks the index-finger tip and thumb tip: when they are far apart, it sends a volume-up key; when they are close together, it sends volume down.

## Features

- Tracks hand landmarks in a live webcam feed using MediaPipe.
- Draws hand landmarks and highlights the two fingertips used for the gesture.
- Sends system volume key presses through PyAutoGUI.
- Runs locally using your webcam; no network service is required by the script.

## Requirements

- Python installed on your computer
- A working webcam
- The Python packages `opencv-python`, `mediapipe`, and `pyautogui`

## Setup

Save the provided script as `hand_volume_control.py`, then install its dependencies:

```sh
python -m pip install opencv-python mediapipe pyautogui
```

If your system uses `python3` to run Python, replace `python` with `python3` in the commands.

## Run

```sh
python hand_volume_control.py
```

The script opens the default camera (device index `0`) and displays the webcam feed. Show your hand so the camera can detect it. Press **Esc** while the preview window is active to stop the program and release the camera.

## Gesture behavior

The script measures the distance between the thumb tip and index-finger tip. Its current logic sends a volume-up key press when the scaled distance is greater than `50`; otherwise, it sends volume down. Since this check happens on every video frame, holding a gesture may send repeated key presses. The exact response depends on the operating system and its handling of volume keys.

## Help

Check that the webcam is connected and available to Python, and that your operating system allows the application to use the camera and send keyboard events. For dependency-specific help, see the documentation for [OpenCV](https://docs.opencv.org/), [MediaPipe](https://ai.google.dev/edge/mediapipe/solutions/guide), and [PyAutoGUI](https://pyautogui.readthedocs.io/).

## Maintainers and contributions

No maintainer contact, contribution guide, or license information is provided with the supplied script. For changes, submit a focused pull request to the repository hosting this project, including a description and any relevant test details. Check with the repository owner for contribution and licensing policies.
