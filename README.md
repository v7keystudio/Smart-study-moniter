🧠 Smart Study Monitor

A real-time AI-powered study monitoring system built with Python, OpenCV, CVZone, MediaPipe Face Mesh, YOLOv8, and Pygame.

The system uses your webcam to monitor study sessions and automatically warns you when it detects sleepiness, a covered/missing face, or mobile-phone usage.

✨ Features

- 😴 Sleep Detection — Detects prolonged eye closure and displays a wake-up warning.
- 🙈 Face Covered Detection — Detects when the face disappears from the camera for a certain period.
- 📱 Phone Detection — Uses YOLOv8 to detect a mobile phone through the webcam.
- 🔊 Audio Alerts — Plays different alarm sounds for different situations.
- 🎥 Real-Time Webcam Monitoring — Processes the camera feed continuously.
- ⚡ Lightweight YOLOv8 Model — Uses "yolov8n.pt" for fast object detection.
- 🖥️ Live Warning Overlay — Displays warnings directly on the camera feed.

🛠️ Technologies Used

- Python
- OpenCV
- CVZone
- MediaPipe Face Mesh
- Ultralytics YOLOv8
- Pygame
- NumPy

🔍 How It Works

1. Face & Eye Detection

The application uses CVZone's Face Mesh detector to locate facial landmarks.

It calculates an eye-to-face distance ratio to determine whether the user's eyes have remained closed for a sufficient number of frames.

The project uses a sleep threshold of 15 frames.

2. Face Covered Detection

If no face is detected, the application starts counting frames.

After the configured threshold is reached, it considers the face covered or missing and triggers a warning.

3. Phone Detection

YOLOv8 detects objects in the webcam feed. The application specifically checks for the "cell phone" class and requires a confidence score above 50% before triggering the phone warning.

4. Smart Alarm Priority

The warning system follows this priority:

1. 🙈 Face Covered
2. 😴 Sleep Detection
3. 📱 Phone Detection

Different audio files are played depending on the detected condition.

📁 Project Structure

Smart-Study-Monitor/
│
├── app.py
├── yolov8n.pt
├── face_landmarker.task
├── hand_landmarker.task
│
├── alarm.mp3
├── faudio.mp3
├── paudio.mp3
│
├── .gitattributes
└── README.md

⚙️ Installation

1. Clone the repository

git clone https://github.com/v7keystudio/Smart-study-moniter.git
cd Smart-Study-Monitor

2. Install dependencies

pip install opencv-python cvzone ultralytics pygame

If your environment requires MediaPipe explicitly:

pip install mediapipe

3. Make sure the required files are present

Keep these files in the project directory:

yolov8n.pt
alarm.mp3
faudio.mp3
paudio.mp3

The Python application loads these audio files and the YOLO model directly by filename.

▶️ Run the Project

Run:

python app.py

Your webcam should open automatically.

Keyboard Control

Press:

Q

to quit the application.

🚨 Warning Messages

Detection| Warning
😴 Sleep| "WAKE UP & STUDY!"
🙈 Face Covered| "DONT COVER YOUR FACE!"
📱 Phone| "PUT THE PHONE AWAY!"

The application also keeps the corresponding warning visible while its alarm audio is finishing.

🎯 Use Cases

This project can be useful for:

- 📚 Self-study monitoring
- 🧑‍💻 Coding/study sessions
- 🎓 Student productivity
- 📵 Reducing phone distractions
- 😴 Preventing accidental sleep during study
- 🤖 Learning real-time computer vision

⚠️ Limitations

- Requires a working webcam.
- Poor lighting can reduce face-detection accuracy.
- Phone detection depends on YOLO confidence and camera visibility.
- Eye-ratio thresholds may need adjustment for different users.
- Audio files must remain available in the expected project directory.
- The system is intended as a productivity tool, not a medical sleep-detection system.

🚀 Future Improvements

Possible improvements include:

- 📊 Study-session statistics
- ⏱️ Pomodoro timer
- 📈 Productivity dashboard
- 📝 Session history
- 🔐 User profiles
- 🌐 Web-based dashboard
- 🤖 More accurate drowsiness detection
- 🎯 Customizable detection thresholds
- 📱 Better phone-use tracking
- ☁️ Cloud-based study analytics

👨‍💻 Author

V7KEY STUDIO

Built with Python and Computer Vision.

---

⭐ If you find this project useful, consider giving the repository a star!

📜 License

This project is provided for educational and personal use.
