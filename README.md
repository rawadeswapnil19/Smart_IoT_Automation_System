# Smart IoT Automation System

### ESP32-Based Smart Distance Monitoring and Obstacle Alert System

## 1. Project Overview

The Smart IoT Automation System is an ESP32-based project that detects nearby objects using an HC-SR04 ultrasonic sensor.

The system continuously measures the distance between the sensor and an object. Based on the measured distance, it automatically identifies the object's proximity level and activates a buzzer when an object enters the danger zone.

An OLED display provides real-time distance and system status information.

The ESP32 also connects to Wi-Fi and uploads sensor readings to the ThingSpeak cloud platform for remote monitoring.

## Wokwi Simulation

[Click here to view and run the project on Wokwi](https://wokwi.com/projects/477967044546918401)

## 2. Objectives

- Develop an automatic distance monitoring system.
- Detect nearby obstacles using an ultrasonic sensor.
- Implement IF-ELSE-based automation logic.
- Provide visual and audible alerts.
- Display real-time sensor readings.
- Monitor sensor data through an IoT cloud dashboard.

## 3. Hardware and Software Requirements

| Component | Purpose |
|---|---|
| ESP32 DevKit V1 | Main controller |
| HC-SR04 | Ultrasonic distance measurement |
| OLED 128×64 | Real-time information display |
| Buzzer | Audible warning |
| Wokwi | Circuit simulation |
| Arduino IDE | Code development |
| ThingSpeak | Cloud monitoring |

## 4. Pin Connections

| Component | ESP32 Pin |
|---|---|
| HC-SR04 TRIG | GPIO 5 |
| HC-SR04 ECHO | GPIO 18 |
| OLED SDA | GPIO 21 |
| OLED SCL | GPIO 22 |
| Buzzer (+) | GPIO 25 |

## 5. Working Principle

1. The HC-SR04 ultrasonic sensor sends ultrasonic waves.
2. The sensor receives the reflected waves from nearby objects.
3. The ESP32 calculates the distance using the measured echo time.
4. IF-ELSE conditions determine the object's status.
5. The OLED displays distance and status.
6. The buzzer activates when an object enters the danger zone.
7. The ESP32 uploads sensor readings to ThingSpeak through Wi-Fi.

## 6. Automation Logic

| Distance | Status | Buzzer |
|---|---|---|
| Above 50 cm | SAFE | OFF |
| 20–50 cm | OBJECT NEAR | OFF |
| Below 20 cm | DANGER | ON |

The system automatically changes its status according to the measured distance.

## 7. IoT Integration

The ESP32 connects to the Wi-Fi network and sends sensor data to the ThingSpeak cloud platform.

Three fields are configured:

- Field 1: Distance (cm)
- Field 2: Object Status
- Field 3: Buzzer Status

Data is uploaded approximately every 20 seconds, allowing remote monitoring through the ThingSpeak dashboard.

## 8. Testing and Results

The system was tested under three different distance conditions.

| Test | Distance | Expected Result |
|---|---|---|
| SAFE | 70 cm | Buzzer OFF |
| OBJECT NEAR | 35 cm | Buzzer OFF |
| DANGER | 10 cm | Buzzer ON |

The system successfully identified the different proximity levels and updated the OLED display, buzzer, and cloud dashboard accordingly.

## 9. Repository Structure

```text
Smart_IoT_Automation_System/
│
├── Circuit/
│   └── diagram.json
│
├── Code/
│   └── sketch.ino
│
├── Screenshots/
│   ├── SAFE.png
│   ├── NEAR.png
│   └── DANGER.png
│
├── README.md
├── TASK 2 CIRCUIT SS.jpeg
├── Task3_Smart_IoT_Automation_Working_Explanation.docx
│
├── task 3 thingspeak danger.png
├── task 3 thingspeak near.png
└── task 3 thingspeak safe.png
```

## 10. Applications

- Smart parking assistance.
- Obstacle detection systems.
- Safety monitoring.
- Distance-based warning systems.
- Smart automation applications.

## 11. Conclusion

The Smart IoT Automation System successfully demonstrates the integration of embedded systems, ultrasonic sensing, automation logic, OLED monitoring, and IoT cloud connectivity using ESP32.

The project provides real-time obstacle detection, automatic warning alerts, and remote monitoring through ThingSpeak.
