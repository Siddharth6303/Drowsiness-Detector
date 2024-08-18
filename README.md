Drowsiness Detection for Drivers to Prevent Accidents
Overview
This project aims to develop a real-time drowsiness detection system for drivers, using computer vision and deep learning techniques. The system monitors the driver's eyes through a webcam and sounds an alarm if it detects prolonged eye closure, which could indicate that the driver is drowsy. This project is crucial in preventing accidents caused by drowsy driving, which is a significant concern in road safety.

Features
Real-Time Eye Detection: The system uses Haar Cascade classifiers to detect the driver's eyes in real-time from webcam footage.
Deep Learning-Based Classification: A Convolutional Neural Network (CNN) is trained to classify the state of the eyes (open or closed) based on input from the webcam.
Drowsiness Detection: If the system detects that both eyes are closed for a continuous period, it triggers an alarm to alert the driver.
Visual Alert: In addition to the sound alarm, the system displays a visual alert by drawing a red, pulsating rectangle around the video feed.
Customizable Parameters: Thresholds for drowsiness detection and alarm sensitivity can be adjusted to meet specific needs.
Installation
Clone the Repository:


git clone https://github.com/yourusername/drowsiness-detection.git
cd drowsiness-detection
Install the Required Packages:


pip install -r requirements.txt
Download Pre-trained Model:

Place the pre-trained model cnnCat2.h5 in the models/ directory. You can either use the provided model or train your own using the provided training script.
Run the Application:


python drowsiness_detection.py
Dataset
The model was trained on a custom dataset of grayscale images, categorized into "open" and "closed" eye states. The images are resized to 24x24 pixels for processing. The dataset is structured as follows:


data/
├── train/
│   ├── open/
│   │   ├── img1.jpg
│   │   ├── img2.jpg
│   │   └── ...
│   └── closed/
│       ├── img1.jpg
│       ├── img2.jpg
│       └── ...
└── valid/
    ├── open/
    │   ├── img1.jpg
    │   ├── img2.jpg
    │   └── ...
    └── closed/
        ├── img1.jpg
        ├── img2.jpg
        └── ...
Model Architecture
The CNN model used in this project consists of the following layers:

Convolutional Layers: Three layers with ReLU activation and 32/64 filters of size 3x3.
Pooling Layers: MaxPooling layers with a pool size of 1x1 (not reducing dimensionality but selecting strong features).
Dropout Layers: Applied to prevent overfitting (0.25 and 0.5).
Flatten and Dense Layers: Fully connected layers to make predictions, with a final softmax layer for output probabilities.
Usage
Once the system is running, it will continuously monitor the driver's eye state using the webcam:

If both eyes are closed for more than a set threshold, an alarm will sound to wake the driver.
A red, pulsating rectangle will appear around the video feed as a visual alert.
Customization
You can adjust the following parameters to fine-tune the system:

Threshold for drowsiness detection (score): Adjust the number of frames both eyes need to be closed before the alarm is triggered.
Alarm sound: Replace the alarm.wav file with any custom sound you prefer.
Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure your code is well-documented and follows the project’s coding standards.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments
The project leverages the Keras library for deep learning and OpenCV for real-time computer vision.
Haar Cascade classifiers used in this project are provided by OpenCV.
Feel free to customize the sections according to your specific project details!
