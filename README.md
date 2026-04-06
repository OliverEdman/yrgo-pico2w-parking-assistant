![Status](https://img.shields.io/badge/status-work--in--progress-orange)

IoT Parking Assistant - MicroPython Project
🎯 Project Purpose

This project was developed as a core part of my Embedded Systems education at YRGO. The primary goal was to implement a full-stack IoT solution, focusing on MQTT connectivity, Wi-Fi stability, and real-time sensor data processing using MicroPython.
🚀 Overview

* Proximity Task: Real-time distance measurement using an Ultrasonic sensor (HC-SR04).

* Visual Feedback: LED logic where blink frequency is based on distance to an object.

* Dual-Vehicle Menu: An interactive button allowing users to toggle between two car profiles (Car 1 & Car 2).

* IoT Connectivity: Data streaming to a remote MQTT Broker (test.mosquitto.org) for remote monitoring.

* Network Resilience: Implementation of Wi-Fi reconnection logic and exception handling to ensure system uptime.

🛠️ Tech Stack & Hardware

* Microcontroller: Raspberry Pi Pico 2W.

* Language: MicroPython

* Communication & Protocols: MQTT (umqtt.simple), Wi-Fi (Network library), Digital I/O.

* Key Components: HC-SR04 Ultrasonic Sensor, LED Indication, Tactile Push-button (Menu).

📁 Project Structure
```bash

.
├── 📂 src                  # Main application logic
│   └── main.py             # Entry point & Hardware initialization
├── 📂 lib                  # External libraries
│   └── umqtt_simple.py     # MQTT for MicroPython
├── 📄 README.md            # Project documentation
├── 📄 .gitignore           # Files to ignore
├── 📄 LICENSE              # MIT License
└── 📝 NOTES.md             # Pinout diagrams etc
```
📡 MQTT Implementation

The system sends live data to the following address (topic):
yrgo/mqtt/picoOliver/avstand/value

* Data: Sends the distance in centimeters (cm).

* Frequency: Sends a new update every second (1000ms).

* Status: Shows which car profile is currently active.

⚙️ Setup & Installation

* Wi-Fi Config: Enter your network name and password in the main.py file.

* Library: Make sure the file umqtt_simple.py is saved in the /lib folder on your Pico.

* How to Run: Use Thonny to start the code. To make it start automatically when the Pico gets power, name the file main.py.

* Check Data: Use a program like MQTT Explorer to see the values arriving at the server.
