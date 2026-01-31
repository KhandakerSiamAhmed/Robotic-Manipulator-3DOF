# 3 DOF Robotic Arm with ESP32

## Overview
This project involves building a 3 Degree of Freedom (DOF) robotic arm using an ESP32 microcontroller, MG996R servos with analog feedback, and a current-sensing gripper. The goal is to implement Inverse Kinematics (IK) directly on the ESP32 and eventually integrate Computer Vision and a Chatbot for high-level control.

**[Check Project Progress Here](tasks.md)**

## Features
- **3 DOF Design**: Base rotation + 2 Link rotations.
- **Smart Gripper**: Force detection using current sensing.
- **Analog Feedback**: Closed-loop control for precise positioning.
- **Inverse Kinematics**: Cartesian coordinate control (x, y, z) solved on-chip.
- **Future Support**: Digital Twin, Computer Vision, and Voice Control.

## Hardware Specifications (BOM)
- **Microcontroller**: ESP32 S3-WROOM-1
- **Actuators**: 
  - 3x MG996R Analog Feedback Servos (with built-in feedback wire)
  - 1x Servo for Gripper (MG996R Analog Feedback or standard MG90S)
- **Power System**:
  - **Main Source**: 12V 10A SMPS
  - **Servo Power**: 250W 8A Buck Converter XH-M404 (Adjustable DC-DC Step-Down, XL4016)
  - **ESP Power**: Mini MP1584EN DC-DC Buck (5V Step-Down)
- **Sensors**:
  - Analog feedback from servos
  - Current Sensor (ACS712 or INA219) for gripper feedback (optional/planned)

- **Body**: 3D Printed (PLA/PETG)

## Folder Structure
- `/firmware`: PlatformIO/Arduino code for ESP32
- `/hardware`: SolidWorks parts, STL files for 3D printing, Schematics
- `/software`: PC-side software (Python, AI integration)
- `/docs`: Calculations, Kinematics diagrams, Datasheets

## Getting Started
1. **Hardware**: Print parts from `/hardware` and assemble.
2. **Firmware**: Open `/firmware` in VS Code with PlatformIO and upload to ESP32.
3. **Control**: Open the serial monitor to send commands.
