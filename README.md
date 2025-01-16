# Volume-Modulation-Using-Hand-Gestures

Hand Gesture Volume Control
This project implements a hand gesture-based system to control the system's audio volume using a webcam. The application utilizes MediaPipe Hands for real-time hand tracking and gesture recognition and PyCaw to interface with the system's audio controls.

Features
Real-Time Hand Tracking: Detects and tracks a single hand in the video feed.
Volume Control: Adjusts the system volume based on the distance between the thumb tip and index fingertip.
Visual Feedback: Displays the detected hand landmarks and the current volume percentage on the screen.
Requirements
Install the required Python libraries before running the code:

bash
Copy
Edit
pip install opencv-python mediapipe pycaw comtypes
How It Works
Hand Detection:

The MediaPipe Hands module identifies hand landmarks in the video feed.
The landmarks for the thumb tip and index fingertip are used for volume control.
Volume Mapping:

The Euclidean distance between the thumb tip and index fingertip is calculated.
The distance is mapped to the system volume range using PyCaw.
Volume Adjustment:

The calculated volume is clamped within the system's allowable range.
The system volume is updated in real-time as the distance between the fingers changes.
Visual Output:

Hand landmarks and the thumb-index distance are drawn on the video feed.
The current volume percentage is displayed on the screen.
Usage
Clone this repository and navigate to the project directory:

bash
Copy
Edit
git clone https://github.com/your-username/hand-gesture-volume-control.git
cd hand-gesture-volume-control
Run the script:

bash
Copy
Edit
python volume_control.py
Control the Volume:

Move your thumb and index finger closer to decrease the volume.
Move your thumb and index finger apart to increase the volume.
Press 'q' to exit the application.

File Structure
hand-gesture-volume-control/
├── volume_control.py       # Main script for hand gesture volume control
└── README.md               # Project documentation

Notes
Ensure your webcam is functional and accessible to the script.
Adjust the sensitivity by modifying the distance scaling in the code:
python
Copy
Edit
vol = min_vol + (max_vol - min_vol) * (distance / 200)  # Adjust 200 as needed
Known Issues
The system may not work well in low-light conditions due to reduced tracking accuracy.
Ensure no other application is using the webcam.
