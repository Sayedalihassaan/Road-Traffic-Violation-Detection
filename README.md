## Road Traffic Violation Detection
This project implements a real-time road traffic violation detection system using YOLOv10 for vehicle detection and OpenCV for traffic light color detection. It identifies cars that cross a predefined area during a red traffic light, triggers an alarm, and sends violation images to a Telegram bot. Additionally, a partial implementation for wrong-way driving detection is included, demonstrating mouse event handling for video analysis.
## Features

Traffic Light Detection: Detects green and red traffic lights using HSV color thresholding.
Vehicle Detection: Uses YOLOv10 to detect cars in video frames with confidence scoring.
Violation Detection: Identifies cars crossing a predefined area during a red light.
Real-Time Alerts: Plays an alarm sound and sends violation images via Telegram.
Visualization: Displays bounding boxes, traffic light labels, and violation alerts on the video feed.
Wrong-Way Detection: Includes a basic setup for detecting wrong-way driving with mouse coordinate tracking.

## Requirements

Python 3.7+
Libraries:
ultralytics
opencv-python
numpy
cvzone
pygame
telepot


A YOLOv10 model file (e.g., yolov10s.pt)
A coco.txt file with COCO class names (included in the repository)
An alarm.wav file for violation alerts (included or user-provided)
A Telegram bot token and chat ID for notifications

Install the required dependencies using:
pip install ultralytics opencv-python numpy cvzone pygame telepot

Installation

Clone the repository:git clone https://github.com/your-username/road-traffic-violation-detection.git
cd road-traffic-violation-detection


Install the dependencies:pip install -r requirements.txt


Download a YOLOv10 model (e.g., yolov10s.pt) from the Ultralytics YOLO repository and place it in the project directory.
Ensure coco.txt and alarm.wav are in the project directory (included in the repository).
Place your input video files (e.g., tr.mp4 for violation detection, wrongway.mp4 for wrong-way detection) in the project directory.
Set up a Telegram bot:
Create a bot using BotFather on Telegram to get a bot token.
Obtain your chat ID by messaging the bot and using a service like @userinfobot.
Update the bot token and chat ID in the notebook under the Telegram bot section.



Usage

Prepare the Environment:

Ensure yolov10s.pt, coco.txt, alarm.wav, and input videos (tr.mp4, wrongway.mp4) are in the project directory.
The Tracker class (assumed to be in tracker.py) must be available for object tracking.


Run the Notebook:

Open the Road Traffic Violation Detection.ipynb notebook in Jupyter Notebook or JupyterLab:jupyter notebook "Road Traffic Violation Detection.ipynb"


Execute the cells sequentially to run either:
Traffic Violation Detection (first code cell):
Detects traffic lights and cars in tr.mp4.
Identifies violations when cars enter the area defined by [(274, 430), (840, 434), (836, 373), (322, 366)] during a red light.
Visualizes results with bounding boxes, labels, and violation alerts.
Sends violation images to Telegram and plays alarm.wav.


Wrong-Way Driving Detection (second code cell):
Loads wrongway.mp4 and displays mouse coordinates for video analysis.
Note: YOLO model integration is commented out and requires completion.






Output:

Traffic Violation Detection:
Video feed shows traffic light status, car bounding boxes with confidence scores, and violation alerts.
Violation images are saved as Car_Traffic_Violation_Detection.jpg and sent to Telegram.
Press q to exit the video display.


Wrong-Way Driving Detection:
Displays the video with mouse coordinates printed to the console.
Press q to exit.




Customization:

Adjust the HSV color ranges (lower_bound_green, upper_bound_green, lower_bound_red, upper_bound_red) for traffic light detection.
Modify the violation area coordinates (area) to suit your video.
Update the Telegram bot token and chat ID in the notebook.
For wrong-way detection, integrate the YOLO model and define detection logic as needed.



Project Structure
road-traffic-violation-detection/
│
├── Road Traffic Violation Detection.ipynb  # Main Jupyter Notebook
├── tracker.py                              # Custom Tracker class (assumed)
├── coco.txt                               # COCO class names
├── yolov10s.pt                            # YOLOv10 model (to be downloaded)
├── alarm.wav                              # Alarm sound file
├── tr.mp4                                 # Input video for violation detection
├── wrongway.mp4                           # Input video for wrong-way detection
├── requirements.txt                       # Required dependencies
└── README.md                              # This file

Notes

The tracker.py file is not included in the provided document but is assumed to contain the Tracker class. Ensure it is available or implement a compatible tracking solution.
The violation detection area and HSV thresholds are tuned for the provided video (tr.mp4) at resolution 1020x700. Adjust for different videos or resolutions.
The wrong-way detection cell is incomplete (YOLO model integration is commented out). Complete it by loading the model and defining detection logic.
Ensure the Telegram bot token and chat ID are valid to receive violation images.

Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Commit your changes (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments

Ultralytics YOLO for the YOLOv10 model.
cvzone for visualization utilities.
telepot for Telegram bot integration.
The open-source community for providing invaluable tools and resources.

Contact
For questions or issues, please open an issue on GitHub or contact saiedhassaan2@gmail.com

