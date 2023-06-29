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
