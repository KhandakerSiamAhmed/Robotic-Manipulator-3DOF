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
- **Microcontroller**: ESP32 DevKit V1
- **Actuators**: 
  - 3x MG996R High Torque Servos (Modded for analog feedback or specific feedback models)
  - 1x Servo for Gripper (MG996R or MG90S)
- **Sensors**:
  - Current Sensor (ACS712 or INA219) for gripper feedback
- **Power Supply**: 5V/10A Power Supply (Servos are power hungry!)
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
