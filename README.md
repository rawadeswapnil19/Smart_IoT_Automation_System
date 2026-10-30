Smart IoT Automation System

ESP32-Based Smart Distance Monitoring and Obstacle Alert System

1. Project Overview

The Smart IoT Automation System is an ESP32-based project that detects nearby objects using an HC-SR04 ultrasonic sensor.

The system automatically measures distance, identifies the object's proximity level, activates a buzzer when an object enters the danger zone, and displays real-time information on an OLED display.

Using Wi-Fi connectivity, the ESP32 also sends sensor data to the ThingSpeak cloud platform for remote monitoring.

2. Objectives

- Develop an automatic distance monitoring system.
- Detect nearby obstacles using an ultrasonic sensor.
- Implement IF-ELSE-based automation logic.
- Provide visual and audible alerts.
- Monitor sensor readings through an IoT cloud dashboard.

3. Components Used

Component| Purpose
ESP32 DevKit V1| Main controller
HC-SR04| Ultrasonic distance measurement
OLED 128×64| Real-time information display
Buzzer| Audible warning
Wokwi| Circuit simulation
ThingSpeak| Cloud monitoring

4. Pin Connections

Component| ESP32 Pin
HC-SR04 TRIG| GPIO 5
HC-SR04 ECHO| GPIO 18
OLED SDA| GPIO 21
OLED SCL| GPIO 22
Buzzer (+)| GPIO 25

5. Automation Logic

The system operates according to three distance conditions.

Distance| Status| Buzzer
Above 50 cm| SAFE| OFF
20–50 cm| OBJECT NEAR| OFF
Below 20 cm| DANGER| ON

If the sensor produces no valid reading, the system displays NO READING and keeps the buzzer OFF.

6. IoT Implementation

The ESP32 connects to Wi-Fi and uploads sensor information to ThingSpeak every 20 seconds.

Three fields are configured:

- Field 1: Distance (cm)
- Field 2: Object Status
- Field 3: Buzzer Status

Cloud Data Encoding

Object Status

- 0 = No Reading
- 1 = SAFE
- 2 = OBJECT NEAR
- 3 = DANGER

Buzzer Status

- 0 = OFF
- 1 = ON

7. Software and Tools

- Arduino IDE
- Wokwi Simulator
- ESP32 Arduino Core
- Adafruit GFX Library
- Adafruit SSD1306 Library
- ThingSpeak Cloud Platform

8. Project Structure

Smart-IoT-Automation-System/
│
├── Code/
│   └── sketch.ino
│
├── Circuit/
│   └── diagram.json
│
├── Screenshots/
│   ├── task 3 safe.png
│   ├── task 3 near.png
│   ├── task 3 danger.png
│   └── ThingSpeak screenshots
│
├── Documentation/
│   └── Working_Explanation.docx
│
└── README.md

9. Testing Results

The system was tested using different simulated distances.

Test Distance| Expected Result
70 cm| SAFE – Buzzer OFF
35 cm| OBJECT NEAR – Buzzer OFF
10 cm| DANGER – Buzzer ON

The ESP32 successfully connected to the simulated Wi-Fi network and uploaded sensor data to ThingSpeak.

10. Applications

- Smart parking systems
- Obstacle detection
- Home security
- Industrial safety monitoring
- Robotics and automation

11. Future Improvements

- Mobile application integration
- Real-time mobile notifications
- Physical hardware implementation
- Improved sensor accuracy
- Advanced cloud monitoring

12. Conclusion

This project demonstrates sensor-based monitoring, automatic decision-making, output control, and IoT cloud connectivity using ESP32.

It provides an effective demonstration of how embedded systems and IoT technologies can be combined to develop smart automation applications.

---

Project Category: Embedded Systems and IoT
Controller: ESP32
Simulation: Wokwi
Cloud Platform: ThingSpeak
