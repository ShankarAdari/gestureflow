GestureFlow: Real-Time Hand Gesture Control InterfaceBridging the gap between human intent and digital execution using Computer Vision.

📌 The "Why"In a world of touchscreens, there are many scenarios where touching a device is inconvenient or impossible—surgery rooms, kitchens, or public kiosks. 

GestureFlow solves this by providing a touchless, camera-based control system that is lightweight enough to run on standard hardware without external sensors like Leap Motion.


🚀 Core Features21-

Point Landmark Tracking: Utilizes MediaPipe's palm detection and hand landmark model for precise finger tracking.

Context-Aware Controls: * Media Mode: Play/Pause with a "stop" gesture; Volume control via finger-distance scaling.

Presentation Mode: Slide navigation via left/right swipes.

System Control: Virtual mouse movement and clicking.

Visual HUD: Real-time feedback overlay showing the detected gesture and the corresponding confidence score.

Zero-Latency Processing: Optimized Python pipeline ensuring real-time response on standard CPUs.

🛠️ Tech StackLanguage: Python 3.

xML/CV Libraries: MediaPipe, OpenCV, NumPy.

System Integration: PyAutoGUI / Screen-brightness-control.

Frontend (Demo): Flask / Streamlit for a browser-based dashboard.

🌍 Real-World ApplicationsAccessibility: Empowering users with limited mobility to navigate computers without a physical mouse.

Sterile Environments: Allowing doctors to review medical imaging during surgery without touching hardware.

Smart Home/IoT: A unified interface to control smart devices via a single camera module.

⚙️ How It Works (The ML Logic)The application follows a three-stage pipeline:

Image Processing: Captured frames are converted to RGB and processed to detect hand presence.

Landmark Extraction: The model calculates $x, y, z$ coordinates for 21 key points.
Vector Calculation: The system calculates the distance between landmarks (e.g., Tip of Index to Tip of Thumb) to determine the "Gesture State" using Euclidean distance:$$d = \sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$$
