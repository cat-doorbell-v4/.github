# Cat Doorbell Version 4

## Introduction

Welcome to Cat Doorbell Version 4! This project transforms your decommissioned Pixel phones into dedicated devices that monitor and alert you when your cat wants to come inside. Designed for single-purpose functionality, the Cat Doorbell leverages advanced sound and image recognition technologies to detect your cat's presence and notify you promptly.

## Key Functionalities

### Sound Detection
The Cat Doorbell listens for the sound of your cat meowing when the camera is inactive. This passive listening mode helps conserve the device's resources and prevents overheating. Upon detecting a meow, the device wakes up and activates the camera to visually verify the cat's presence.

### Visual Verification
Once activated, the camera will operate for a 45-second window to identify a cat. In low-light conditions, the device will automatically turn on the flashlight to assist the camera. If a cat is detected within this timeframe, a text message alert is sent to notify you. If no cat is identified, the device returns to passive listening mode, and the flashlight is turned off if it was on.

### Alert System
The alert system is designed to be efficient and user-friendly. Upon detecting a cat, a text message alert is triggered via an HTTP request to an AWS API Gateway REST API. To avoid multiple alerts for the same event, the system pauses for 2 minutes before resuming monitoring. If the flashlight was turned on during the detection, it remains on until the end of this pause period.

## Technical Details

### Sound and Image Processing
The Cat Doorbell employs TensorFlow models for both sound and image recognition to accurately identify cat sounds and appearances.

### Alert Mechanism
The alert mechanism utilizes HTTP requests to an AWS API Gateway REST API to send text message notifications efficiently.

### Device Operation
The application is developed in Kotlin and is optimized to run continuously on Pixel phones, which are always connected to power with their batteries serving as backups.

## Requirements

To run the Cat Doorbell application, you will need:

- Decommissioned Pixel phones (Pixel 3XL and Pixel 4XL are used in this setup)
- Constant power supply to the devices
- Android Studio Jellyfish | 2023.3.1 Patch 1 for development
- TensorFlow models for sound and image recognition
- AWS account for API Gateway REST API setup

## Setup

### Development Environment
Ensure you have the following setup on your development machine:

- Android Studio Jellyfish | 2023.3.1 Patch 1
- OpenJDK 17.0.10
- macOS 14.4.1
- Wi-Fi connectivity for both development and device operation

### Application Deployment
1. Clone the repository to your local machine.
2. Open the project in Android Studio.
3. Build and deploy the application to your Pixel devices.
4. Configure the AWS API Gateway REST API for text message alerts.
5. Place the Pixel 3XL at your garage door and the Pixel 4XL at your patio door.

## Usage

The Cat Doorbell application runs as a kiosk-like setup on your Pixel devices. It operates continuously to monitor for cat sounds and verify their presence visually. Upon detecting a cat, you will receive a text message alert. The application requires manual intervention to stop or modify its operation.

## Network Info

- Ensure both devices are connected to the same home Wi-Fi LAN.
- All remote access will also be within the same Wi-Fi LAN.

## Device Info

- Pixel 3XL (Garage door)
- Pixel 4XL (Patio door)

## Contributions

We welcome contributions to enhance the functionality and performance of Cat Doorbell Version 4. Please fork the repository and submit pull requests for review.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

Thank you for using Cat Doorbell Version 4. We hope this application helps you keep track of your feline friends with ease!
