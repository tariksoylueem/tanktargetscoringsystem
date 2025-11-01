
🛡️ Tank Target Scoring System — First Prototype

📌 Summary

This is the first prototype of a scoring and tracking system that detects a projectile's flight path and velocity using HC-SR04 ultrasonic sensors, and transmits the calculated data via an ESP8266 to an online interface. The system estimates the projectile’s path, speed, and impact point using geometric methods.

🧩 System Architecture

🖥️ Interface Unit

Currently web-based (will be embedded in future versions)

Displays:

Projectile trajectory (2D mapping)

Velocity estimation

Target zone detection

Scoring system

📦 Sensor Unit

Microcontroller: ESP8266

Sensors: 5× HC-SR04 Ultrasonic Distance Sensors

Power Supply: Li-ion rechargeable battery system

Mounting: 3D printed structure (or test rig)

🛠️ Hardware Used

Component

Quantity

Description

ESP8266 (NodeMCU)

1

Wi-Fi MCU for data collection/transmit

HC-SR04

5

Ultrasonic distance sensors

Li-ion Battery

1

Portable power system

Mounting Base

1

For aligning sensor positions

🧠 Software Stack

Language: C (Arduino/ESP core)

Communication: HTTP/WebSocket to transmit data

Frontend (planned): Web UI for real-time tracking and scoring

Backend (planned): Firebase / NodeJS for data collection

🔍 Geometric Detection Logic

Triangulation of distances between sensors to find position

Velocity = Δposition / Δtime (across sensor planes)

Scoring logic uses distance to target center zone

📂 Folder Structure

TankTargetScoringSystem/
├── /docs                → Project reports, diagrams, and explanations
│   ├── CircuitDiagram.pdf
│   ├── GeometricCalculationExplanation.pdf
│   └── SystemWorkflow.pdf
├── /firmware            → ESP8266 code for sensor unit
│   └── main.ino
├── /images              → Real device photos, schematics, UI visuals
│   ├── device_real.jpg
│   ├── ui_mockup.png
│   └── sensor_alignment.jpg
├── /web_interface       → Web interface files (HTML/CSS/JS)
├── README.md            → Project description (this file)
└── LICENSE              → Open-source license (MIT recommended)

📸 Visual References

images/device_real.jpg: Assembled prototype photo

images/sensor_alignment.jpg: Top view sensor layout

images/ui_mockup.png: Planned interface

🧮 Scoring Logic

Hit zones (center, near-center, edge) assigned scores: 10, 7, 3, 0

If projectile impacts within 3cm of center: score = 10

Scoring calculated in real-time and sent to frontend

🧪 Future Plans

Replace web interface with local screen (e.g. TFT via ESP32)

Integrate machine learning to predict hit points more accurately

Multi-projectile support (frame-by-frame scoring)

📄 License

Licensed under the MIT License.

Developed by [Your Name / Team Name], 2025
Part of experimental tracking and scoring research for embedded systems


