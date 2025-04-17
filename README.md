![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)
# Emergency Activation in Automobiles Using IOT
This repository showcases the implementation of a **Car Accident Detection and Notification System (CADANS)**. The system leverages **Arduino Uno**, **Bluetooth communication**, **sensor data**, and a custom Android app created with **MIT App Inventor** to detect accidents and send emergency notifications with GPS coordinates.

---

## 🛠️ Hardware & App Setup

To **demonstrate CADANS in a simulated environment**, the system was implemented using **Arduino Uno** and various sensors to detect crash-like events and communicate with the **HELP Android app** built using **MIT App Inventor**.

### 🔌 Components Used

- **Arduino Uno** – Microcontroller for sensor input and decision-making.
- **HC-05 Bluetooth Module** – Wireless communication with the HELP mobile app.
- **Tilt Sensor** – Detects orientation changes to simulate a vehicle flipping or impact.
- **Flame Sensor** – Detects fire or high heat near the crash site.
- **Power Supply** – 9V battery or USB for powering the Arduino.
- **Smartphone** – Installed with the custom `HELP.apk` for receiving alerts and sending SMS with GPS coordinates.

---

### 🔧 Arduino Setup

1. **Tilt Sensor** is connected to a digital pin (e.g., D2). It monitors for sudden angular changes, indicating vehicle tilting or overturning.
2. **Flame Sensor** is connected to another digital pin (e.g., D3) to detect possible fires after a crash.
3. **HC-05 Bluetooth Module**:
   - **VCC** to 5V
   - **GND** to GND
   - **TX** to Arduino RX (D0)
   - **RX** to Arduino TX (D1)
4. The Arduino reads sensor values and sends specific signal data over Bluetooth to the smartphone when:
   - Flame is detected.
   - Vehicle tilt is detected.
   - These conditions simulate a post-accident scenario.

5. Arduino Sketch (code) listens to the sensor inputs and sends a Bluetooth signal like `ALERT#` to the phone.

---

### 📱 Android Application: HELP.apk

- Created using **MIT App Inventor**, this app acts as the front-end interface for receiving emergency notifications.
- When the app detects an accident notification via Bluetooth, it:
  1. Confirms the accident and sends the notification to emergency contacts.
  2. Uses the phone’s GPS to track the accident location and sends coordinates to predefined emergency contacts via SMS.
  3. Optionally, allows the user or bystanders to record a video or take pictures of the accident scene, which is then sent to emergency responders.

---

## 💻 Software Setup

### Arduino Code

The Arduino code can be found in the repository under the `ArduinoCode` directory. The main logic for reading the sensors and sending notifications is handled in the `CADANS.ino` file. This file uses the `HC-05` Bluetooth module to send accident detection signals to the phone.

### MIT App Inventor Project

The `HELP.apk` is the compiled version of the app developed using **MIT App Inventor**. This app communicates with the Arduino Bluetooth module to receive accident data. 

You can find the MIT App Inventor project source files in the `AppInventorProject` directory. These files can be opened and modified in MIT App Inventor (https://appinventor.mit.edu/).

The application:
- Uses Bluetooth to connect to the Arduino.
- Receives accident notifications and sends SMS alerts with GPS coordinates to emergency contacts.
- Includes features like:
  - Video and photo capture of accident scenes.
  - Confirmation screen for accident verification to avoid false positives.

---

## 📦 Installation

### Hardware Installation

1. **Arduino Uno**: Connect the components as outlined in the Arduino setup section.
2. **HC-05 Bluetooth Module**: Ensure correct wiring for Bluetooth communication.
3. **Sensors**: Attach the **Tilt Sensor** and **Flame Sensor** to the Arduino.
4. Power the Arduino with a suitable power source.

### App Installation

1. Download the `HELP.apk` file from the repository.
2. Install the APK on your Android smartphone.
3. Pair your phone with the Arduino Bluetooth module (HC-05) through the phone’s Bluetooth settings.

### Running the System

1. **Power on the Arduino**: Ensure the Bluetooth module is connected.
2. **Launch the HELP app**: Open the app on your phone.
3. The app will start listening for Bluetooth signals from the Arduino.
4. **Accident Detection**: When the sensors detect an accident-like event (e.g., a significant tilt or fire), the Arduino sends an alert to the app.
5. **Send Notification**: The app confirms the accident and sends an SMS with the GPS coordinates of the accident to predefined emergency contacts.

---

## ⚠️ Limitations & Future Work

### Limitations

1. **Real Crash Testing**: It is difficult to perform real-world crash tests due to safety concerns. However, simulated testing is used to validate the system.
2. **False Positives**: Sensors might occasionally trigger false positives (e.g., due to loud sounds or vibrations). The system includes a confirmation screen to mitigate this.
3. **Sensor Accuracy**: The threshold for detecting crashes, such as a 3G acceleration value, may not always be perfect in real-world scenarios.

### Future Work

1. **Improving Detection Accuracy**: Further work can focus on using **Activity Recognition** algorithms to determine if the user is inside or outside the car during low-speed events.
2. **Voice Recognition**: Adding a voice recognition module can help distinguish between an airbag deployment and benign noise to reduce false positives.
3. **Enhanced Communication Protocols**: Integrating more robust communication systems for better reliability and signal transmission.

---

## 📄 Conclusion

The **Car Accident Detection and Notification System (CADANS)** demonstrates an integrated approach to emergency response using readily available hardware like Arduino, sensors, and Bluetooth communication. The system can detect crashes, send alerts to emergency contacts with location data, and allow for further accident verification using photos or videos. 

---

## 📚 References

- MIT App Inventor (https://appinventor.mit.edu/)
- Arduino Uno (https://www.arduino.cc/)
- HC-05 Bluetooth Module documentation

---

## 🤝 Contributing

If you’d like to contribute, feel free to fork this repository, make changes, and submit a pull request. All contributions are welcome!

---

## 📬 Contact

For any questions or suggestions, please feel free to reach out to me at [hnshubodaya@gmail.com/Contact Information].
