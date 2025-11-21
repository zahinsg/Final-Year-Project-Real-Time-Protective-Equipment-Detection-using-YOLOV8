This project utilizes computer vision (YOLO via Ultralytics) to perform real-time object detection using a webcam. It is integrated with a Telegram bot to send alerts or notifications based on detection events.
📋 Prerequisites
Before running the project, ensure you have the following installed:
Python 3.8+
An IDE (VS Code, PyCharm, etc.)
A working webcam (integrated or external via DroidCam)
⚙️ Installation & Setup
1. File Setup
Ensure you have the following project files in the same directory:
prototype.py: The main executable script.
best.pt: The trained YOLO model weights.
2. Install Dependencies
Open your terminal or command prompt within your IDE and install the required libraries:
pip install ultralytics opencv-python

🔧 Configuration
1. Telegram Bot Setup
To receive notifications, you need to configure a Telegram Bot:
Open Telegram and search for @BotFather.
Create a new bot using the /newbot command.
Copy the HTTP API Token provided.
Get your Chat ID (you can use a bot like @userinfobot to find this).
2. Update Script Variables
Open prototype.py in your IDE and update the configuration lines:
Model Path (Line 23): Update the path to point to your model file.
# Example:
model = YOLO('path/to/your/best.pt') 


Telegram Credentials (Line 27-28): Insert the credentials you generated in the previous step.
# Example:
TELEGRAM_TOKEN = '123456789:ABCdefGHIjklMNOpqrsTUVwxyz'
CHAT_ID = '987654321'


⚠️ Security Note: Never share your Telegram Token publicly. If you push this code to GitHub, it is recommended to use Environment Variables (.env) instead of hardcoding tokens directly into the script.


🚀 Usage
Enable Camera: Ensure your webcam is active. If you are using a phone as a webcam (e.g., via DroidCam), ensure the connection is established before running the script.
Run the Script: Execute the Python script from your terminal:
python prototype.py


📝 Troubleshooting
Camera Error: If OpenCV cannot open the camera, change the video source index in the code (usually cv2.VideoCapture(0) to cv2.VideoCapture(1)).
Model Not Found: Ensure best.pt is in the exact same folder as prototype.py or provide the absolute file path.


NOTE: the other script is for preprocessing data, if you want to custom trained your data, use at your own will
Operation: The system will open a window displaying the live feed with detection bounding boxes. Telegram alerts will be sent based on the logic defined in the script.
