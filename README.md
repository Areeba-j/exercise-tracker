# Real-time Exercise Tracking Application using Roboflow & MQTT 

![image](https://github.com/user-attachments/assets/1269386c-bf64-4a22-9242-4216e2583e5e)

---

This project is a **real-time exercise tracker** that uses a camera to detect and count push-ups. The tracking system is built using **Roboflow's REST API** for object detection and classification, and **MQTT** for messaging and counting logic.

It processes video frames from a webcam or video file, runs them through Roboflow’s model to detect push-up movements, and publishes the results to an MQTT broker. The application counts push-ups in real-time and displays the count on a web interface.

## Key Features

- **Push-up detection in real-time**: The model detects "pushup" and "pushdown" postures.
- **MQTT Messaging**: Results of each detection are sent to an MQTT broker which drives the counter on a simple HTML dashboard.
- **Live Video Inference**: The system processes video frames live from a webcam or video file.
- **Results Visualization**: Bounding boxes are drawn around detected exercise movements, showing classification and confidence scores on the frame.

## How It Works

1. **Camera Input**: A video feed is captured either from a webcam or a video file.
2. **Frame Processing**: Each frame is resized and sent to the **Roboflow** model for inference.
3. **Object Detection**: Roboflow detects whether the person is in a "pushup" or "pushdown" position.
4. **MQTT Publishing**: The detection result (either "pushup" or "pushdown") is sent to an MQTT broker.
5. **Counter Logic**: A JavaScript-based web interface subscribes to the MQTT topic and updates the push-up counter accordingly.
6. **Video Output**: The processed video with detection boxes is saved locally.

## Frameworks Used

- **Roboflow's Python SDK**: To run inference using a pre-trained model hosted on Roboflow.
- **OpenCV**: For handling video input and output, as well as drawing bounding boxes on frames.
- **MQTT**: A lightweight messaging protocol used to send real-time detection results to a web dashboard.
- **Paho MQTT Client**: Python client for MQTT messaging.
- **HTML/JavaScript**: For creating a simple UI to display the push-up counter live.
- **Python**: For the main logic handling the video feed and API requests.

## Setup Instructions

To get this project up and running on your local machine, follow these steps:

### 1. Clone the repository

```bash
git clone https://github.com/your-github-username/exercise-tracker.git
cd exercise-tracker
```

### 2. Install the required dependencies

You'll need to install the necessary Python libraries, which you can find in the `requirements.txt` file. Install them using pip:

```bash
pip install -r requirements.txt
```

### 3. Roboflow Configuration

You will need a **Roboflow account** and a **trained model** for push-up detection. Once you have those:

- Download the API key and model configuration from your Roboflow account.
- Create a `roboflow_config.json` file in your project directory with the following content:

### 4. Running the Tracker

Once you have everything set up, run the Python script to start processing the video:

```bash
python exercise_tracker.py
```

The system will start the camera, process each frame, and publish the results to the MQTT broker.

### 5. Viewing the Push-Up Counter

Open the `javascript_app.html` file in your browser to see the live push-up counter. This page subscribes to the MQTT topic and updates as you perform push-ups!

### 6. Saving the Output Video

The script also saves the output video with bounding boxes and detection results in the project directory.

## Applications

- **Fitness Tracking**: Automatically count your exercise repetitions (push-ups in this case) without needing to manually track them.
- **Personalized Workouts**: This system can be extended to track other types of exercises, allowing for more personalized fitness routines.
- **Live Feedback**: Provides live visual feedback on your form through bounding boxes and labels, helping to ensure proper posture.

## Future Scope

- **Multiple Exercise Tracking**: Extend the model to detect other exercises like squats, sit-ups, etc.
- **Real-Time Alerts**: Send notifications or voice feedback when posture is incorrect.
- **Fitness Data Dashboard**: Store workout data and visualize trends over time.

## Contributing

Contributions to this project are welcome! Feel free to submit a pull request or open an issue if you have suggestions for improvement.


## Project Links

- **GitHub**: [GitHub Repository](https://github.com/Areeba-j/exercise-tracker.git)
- **LinkedIn**: Check out the project on my [LinkedIn](www.linkedin.com/in/areeba-jamshed)

---
