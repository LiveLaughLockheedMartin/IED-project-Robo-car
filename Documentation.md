# IED-project-Robo-car

#  Self-Driving Trash-Picking Robot Car

An autonomous robot car designed to detect, approach, and pick up obstacles using ultrasonic and IR sensors.  
Equipped with a servo-powered claw, the bot identifies objects, avoids collisions, and performs automated trash collection tasks.

---

##  Project Overview

This robot car combines **ultrasonic distance sensing**, **IR color/object detection**, and **servo-based actuation** to navigate its environment autonomously.  
It can detect nearby obstacles, determine their color (e.g., green or purple), and activate a claw mechanism to pick them up.

The system also supports **laser signal overrides**, allowing users to interrupt current actions and trigger specific operations remotely.

---

##  Features

-  **Dual Ultrasonic Sensors** (at 10 o’clock and 2 o’clock) for obstacle detection  
-  **IR Sensor** (at 12 o’clock) for color and object identification  
-  **Servo-Controlled Claw** for picking up detected objects  
-  **Bidirectional Motor Control** for movement and steering  
-  **Laser Signal Interrupt System** to override current operations  
-  **Modular Arduino C++ Codebase** for easy testing and expansion  

---

##  Hardware Components

| Component | Description |
|------------|-------------|
| Arduino Uno / Nano | Main microcontroller |
| 2 × HC-SR04 Ultrasonic Sensors | Left and right obstacle detection (10° & 2°) |
| IR Sensor | Forward color/object sensing (12°) |
| L298N Motor Driver | Motor control for both wheels |
| 2 × DC Motors | Left and right wheel drive |
| Servo Motor | Controls claw mechanism |
| Laser Detectors (optional) | Trigger manual commands |
| Power Supply | 9 V battery or 2-cell Li-ion pack |

---


##  Code Structure

### `autonomous_mode.ino`
Handles:
- Ultrasonic distance measurement  
- IR color detection  
- Obstacle avoidance  
- Claw control for trash pickup  

### `laser_override_mode.ino`
Handles:
- Detection of laser hits via photodiodes  
- Interrupting the current routine  
- Executing pre-defined response actions  

---

##  Working Principle

1. The robot continuously reads distances from both ultrasonic sensors.  
2. If an obstacle is detected within the threshold range (typically < 30 cm), the robot:
   - Stops  
   - Moves backward slightly  
   - Turns away from the obstacle  
   - Moves forward again  
3. If the IR sensor detects an object of a specific color (green or purple), the servo claw activates to pick it up.  
4. If a laser signal is detected, the robot stops all operations and executes the override routine.

---


##  Future Improvements

- Implement PID-based line following  
- Add Wi-Fi remote control (via HC-05 / ESP8266)  
- Improve color detection using TCS34725 color sensor  
- Add battery voltage monitoring and LED indicators  



