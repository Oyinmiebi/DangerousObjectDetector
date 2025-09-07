# DangerousObjectDetector
This repository describes a project undertaken to detect dangerous objects using a custom YOLOv11 model trained on the DangerousObjects Roboflow dataset. The model runs on a RaspberryPi 4, and lights up an LED/ sounds a buzzer as well as takes and sends a screenshot to relevant personnel when a dangerous object is detected. This is a final project from my Embedded Systems class at NCAIR Cohort 27.

## Components Used
1. Raspberry Pi 4
2. USB Camera
3. LED/Buzzer
4. F-F cables
5. Monitor
6. Keyboard + Mouse

![Circuit](https://github.com/user-attachments/assets/fccaacac-9bad-4915-9a0d-4e963cba203e)

## Methodology:

The dataset used for the project was the roboflow "Dangerous-objects" dataset consisting of 8912 images split across train, test and validation sets. Dangerous objects include pistols, grenades, knives, firearms and rockets. (https://universe.roboflow.com/startup-zn0ol/dangerous-objects-dq94u). We trained our model on this dataset. When a dangerous object is detected, a screenshot of the object along with bounding boxes is sent to relevant personnel and the audio/visual indicator goes off. In this case, a buzzer is attached to a raspberry pi and receieves its "on" signal when an objects is detected.

![Dangerous screenshot](https://github.com/user-attachments/assets/cb363740-b082-4186-974d-3999b05ec4a1)

![InferenceImage](https://github.com/user-attachments/assets/0d91cd76-bc31-4781-8a6d-b5c7ebf2479d)

## Problems Faced:
1. Validation tests run on our model show our recall at 64% which is not good enough for actual implementation.
2. Inference is currently too slow on the Raspberry Pi
3. Yolo models are too heavy for the cpu on the Pi and its RAM is usually not sufficient for more accurate results.

## Future Advancements:
1. Use ncnn models for faster inference on the raspberry pi
2. Train model to reach recall >= 90%
3. Overclock raspberry pi cpu
4. Work on further code optimizations to reduce load on raspberry pi
5. Add an AI accelerator to run inference and speed up detection
