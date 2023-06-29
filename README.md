# object-detection-raspberry-pi
Object Detection with Raspberry Pi and TensorFlow Lite. Real-time detection and classification of objects using Google's pre-trained model. Trigger actions based on detected objects. An accessible and versatile solution for applications such as home automation, security systems, and robotics.

# Object Detection with Raspberry Pi and TensorFlow Lite

This repository contains code and resources for an object detection project using Raspberry Pi, TensorFlow Lite, and Google's object detection model.

## Overview

The object detection system implemented in this project utilizes a Raspberry Pi and TensorFlow Lite to perform real-time object detection. It can detect and classify various objects based on a pre-trained model provided by Google.

## Features

- Real-time object detection using a Raspberry Pi and TensorFlow Lite
- Integration with Google's pre-trained object detection model
- Ability to trigger actions based on detected objects

## Getting Started

### Prerequisites

- Raspberry Pi
- TensorFlow Lite 
- Python 
- Any actuator, led or a buzzer which you want to trigger

### Installation

Clone this repository:

```
   git clone https://github.com/atulakella/object-detection-raspberry-pi
```

To ensure compatibility and avoid version conflicts with existing package libraries on your Raspberry Pi, this project utilizes a virtual environment. By keeping TensorFlow installed within its own environment, it safeguards against overriding any previous TensorFlow installations if any. 
```
   sudo pip3 install virtualenv
```

Now lets create the "rpiod-env" virtual environment by executing the following command:
```
  python3 -m venv rpiod-env
```

This will generate a new directory named "rpiod-env" within the "rpiod" directory, containing all the required package libraries specific to this environment. To activate the environment, execute the following command:
```
  source rpiod-env/bin/activate
```

Please note that each time you open a new terminal, it will be necessary to reactivate the environment by executing the command source rpiod-env/bin/activate after cd-ing into rpiod. This ensures that the environment is active for your current session.


To simplify the installation process, a shell script has been provided that will download and install TensorFlow, OpenCV, and their respective dependencies. While OpenCV is not necessary for running TensorFlow Lite, it is utilized in the object detection scripts included in this repository for image acquisition and drawing detection results.

To run the script effortlessly, execute the following command:
```
  bash requirements.sh
```

The provided shell script will download approximately 400MB of installation files, which may take some time. If you encounter an error, try rerunning the command a few times, as it may be due to a temporary issue with your internet connection or corrupted package data. 
The shell script automatically installs the latest version of TensorFlow. Here I'm using a sample TFLite model provided by Google


To utilize a sample quantized SSDLite-MobileNet-v2 object detection model provided by Google, which is trained on the MSCOCO dataset and converted for TensorFlow Lite, you can download it from the Object Detection page on the official TensorFlow website. 
Please execute the following command to download the sample model:
```
  wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip
```

To unzip the downloaded file and extract its contents into a folder named "Sample_TFLite_model," use the following command. The command will automatically create the folder for you.
```
  unzip coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip -d Sample_TFLite_model
```

Hold tight! The sample model is armed with object-detection awesomeness.

Get ready for some TFLite object detection action! To optimize performance, close any unused applications and ensure your webcam or Picamera is connected.

From the `/home/pi/rpiod` directory, activate the `rpiod-env` environment (check for `(rpiod-env)` in the command prompt). Then, execute the command to run the real-time webcam detection script. The script, `webcam.py`, is compatible with both Picamera and USB webcams. Using the folling command you can do the same
```
  python3 webcam.py --modeldir=Sample_TFLite_model
```
I've developed this code to trigger the activation of an LED connected to GPIO 18 whenever a person is detected. However, feel free to modify the code to trigger any other action or device based on the detection. Let your imagination run wild and customize it to suit your needs!
