# Real-Time-Hand-Gesture-Recognition-Using-OpenCV-and-MediaPipe
The code you've shared is a Python script that uses the OpenCV library and MediaPipe for real-time hand gesture recognition from webcam video input. It's structured to read frames from the webcam, process the images to detect hand landmarks using MediaPipe, and then identify specific gestures based on the position of the fingertips relative to other landmarks like the metacarpophalangeal (MCP) joints. Here’s a breakdown of how the script functions:

1. Import Libraries: The script imports necessary libraries, including OpenCV (`cv2`) for image processing, MediaPipe (`mp`) for hand landmark detection, and NumPy (`np`) for numerical operations.

2. Initialization:
   - MediaPipe drawing utilities and hand solutions are initialized.
   - A `VideoCapture` object is created to capture video from the webcam.

3. Main Loop:
   - The video frames are continuously read from the webcam.
   - Each frame is processed to detect hand landmarks:
     - The frame is flipped horizontally (for mirroring effect) and converted from BGR to RGB color space, as required by MediaPipe.
     - MediaPipe processes the image to detect hand landmarks.
     - The frame is converted back to BGR color space for display.
   - If hand landmarks are detected, additional processing occurs:
     - For each detected hand, the script calculates the coordinates of the fingertips and MCP joints.
     - It defines a bounding box around the detected hand.
     - Predefined gestures are recognized based on the relative positions of the fingertips and MCP joints.
     - Gestures like "Yes", "I Love YOU", "Peace", "No", "Call Me", and "OK" are identified using simple geometric rules.
     - The identified gesture and a bounding box are drawn on the frame.
     - The landmarks and connections are drawn using MediaPipe’s drawing utilities.
   - The annotated frame is displayed in a window.

4. Exit Condition:
   - The loop (and the program) exits when the user presses the ESC key.

5. Cleanup:
   - The webcam is released and all OpenCV windows are closed to clean up resources.
