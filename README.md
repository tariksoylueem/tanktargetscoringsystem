# 🛡️ Tank Target Scoring System — First Prototype

## 📌 Summary
This is the **first prototype** of a scoring and tracking system that detects a projectile's flight path and velocity using **HC-SR04 ultrasonic sensors**, and transmits the calculated data via an **ESP8266** to an **online interface**. The system estimates the projectile’s path, speed, and impact point using geometric methods.

## 🧩 System Architecture

### 🖥️ Interface Unit
- Currently web-based (will be embedded in future versions)
- Displays:
  - Projectile trajectory (2D mapping)
  - Velocity estimation
  - Target zone detection
  - Scoring system

### 📦 Sensor Unit
- **Microcontroller:** ESP8266
- **Sensors:** 5× HC-SR04 Ultrasonic Distance Sensors
- **Power Supply:** Li-ion rechargeable battery system
- **Mounting:** 3D printed structure (or test rig)

## 🛠️ Hardware Used

| Component        | Quantity | Description                             |
|------------------|----------|-----------------------------------------|
| ESP8266 (NodeMCU)| 1        | Wi-Fi MCU for data collection/transmit  |
| HC-SR04          | 5        | Ultrasonic distance sensors             |
| Li-ion Battery   | 1        | Portable power system                   |
| Mounting Base    | 1        | For aligning sensor positions           |

## 🧠 Software Stack
- **Language:** C (Arduino/ESP core)
- **Communication:** HTTP/WebSocket to transmit data
- **Frontend (planned):** Web UI for real-time tracking and scoring
- **Backend (planned):** Firebase / NodeJS for data collection

## 🔍 Geometric Detection Logic
- Triangulation of distances between sensors to find position
- Velocity = Δposition / Δtime (across sensor planes)
- Scoring logic uses distance to **target center zone**

## 📂 Folder Structure
