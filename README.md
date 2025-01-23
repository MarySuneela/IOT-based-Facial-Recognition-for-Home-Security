# IOT-based-Facial-Recognition-for-Home-Security

## Overview

This project implements an advanced home security system that uses facial recognition technology to identify authorized individuals and detect intruders. The system integrates a Haar Cascade Classifier for face detection, Raspberry Pi for image processing, and a GSM module to send SMS alerts to authorized users in the event of unauthorized access. The system leverages facial recognition by training the model with thousands of images to accurately capture and understand facial expressions.

### Key Features:
- **Facial Recognition**: Utilizes the Haar Cascade algorithm to detect faces and authorize entry based on a database of registered faces.
- **SMS Alerts**: Sends real-time SMS alerts when unauthorized access is detected.
- **Intruder Detection**: Detects and alerts when an unauthorized individual attempts to access the premises.
- **IoT Integration**: Allows remote access control and monitoring via IoT technology.
- **Training with Large Image Database**: The system is trained with thousands of images to ensure accurate recognition of facial expressions and features for authorized individuals.

### Project Components
- **`register_face.py`**: This script allows you to capture facial images of authorized individuals and store them in a directory. These images are used for the subsequent training of the face recognition model.
- **`train_faces.py`**: This script uses the images captured by `register_face.py` to train the face recognition model using the Local Binary Pattern Histogram (LBPH) method. It processes thousands of images to create an efficient recognition system.
- **`main.py`**: The main system that integrates real-time video processing to detect faces, compare them with the trained database, and control the door lock and alert system based on the recognition result.

## Installation

### Requirements:
- Raspberry Pi (with camera and GPIO pins)
- Python 3.x
- OpenCV
- RPi.GPIO
- GSM Module (for SMS)
- Relay Module (for controlling door lock)

### Setup:
1. **Install dependencies**:
   Use the following command to install the required libraries:
   ```bash
   pip install opencv-python numpy RPi.GPIO
   ```
2. **Hardware Setup**:
1. Camera: Connect a USB camera to the Raspberry Pi for real-time facial recognition.
2. Relay: Connect a relay to control the electronic door lock.
3. GSM Module: Use a GSM module (e.g., SIM800) to send SMS alerts.

3. **Running the scripts**:
1. Register Faces: Run the following command to capture authorized users' faces:

``` python register_face.py ```

2. Train the Model: Once faces are registered, train the recognition model:

``` python train_faces.py ```

This script processes thousands of images (captured in the register_face.py step) to create a reliable model for facial recognition. It improves the accuracy of the system by incorporating various facial expressions and lighting conditions.

3. Run the System: Start the real-time security system:

``` python main.py ```

## System Architecture
The proposed system consists of the following modules:
1. **Face Registration:** Captures and stores images of authorized users.
2. **Face Recognition:** The captured face is compared with the stored database for authentication.
3. **Intruder Detection:** Detects any unauthorized person using background subtraction.
4. **SMS Alerts:** Sends SMS to authorized users upon detection of an intruder.
5. **Relay Control:** Controls the door lock mechanism based on face recognition.

## System Diagram:
<img width="636" alt="Screenshot 2025-01-22 at 7 25 50 PM" src="https://github.com/user-attachments/assets/5f574357-181a-46a1-b926-98e0d8bb4b63" />


## How It Works:
1. **Face Registration:** Authorized users' faces are captured and stored in a database.
2. **Model Training:** A face recognition model is trained using thousands of images, improving recognition accuracy under various conditions.
3. **Real-Time Face Recognition:** The system captures live video and compares faces with the database.
    * If a match is found, the door is unlocked.
    * If no match is found, an SMS alert is sent, and a buzzer is triggered.

## Applications:
* Home Security: Real-time authentication for access control.
* Banking Security: Can be adapted for use in secure banking systems.
* Attendance Systems: Can be extended to office or school attendance systems.

## Testing and Results
The system has been tested successfully to perform both authorized and unauthorized access detection:
* Authorized Access: When a registered face is detected, the door unlocks automatically.
* Unauthorized Access: If an unknown face is detected, the buzzer sounds, and an SMS alert is sent to the authorized person.
Example Images:
Authorized Access:


<img width="636" alt="Screenshot 2025-01-22 at 7 30 29 PM" src="https://github.com/user-attachments/assets/272c193d-253e-4f1d-92ac-c3716bef05d1" />


Unauthorized Access:


<img width="509" alt="Screenshot 2025-01-22 at 7 31 07 PM" src="https://github.com/user-attachments/assets/e6e2fd0b-e015-408b-a288-734d1339b61b" />


## Future Enhancements:
* **Infrared Imaging:** Incorporate infrared cameras for low-light conditions.
* **Weapon Detection:** Use image processing to detect concealed weapons.
* **Smart Integration:** Integrate with other smart home devices for a fully automated security system.

