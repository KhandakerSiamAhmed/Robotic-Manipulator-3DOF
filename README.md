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
- `/firmware`: ESP32-S3 source code (PlatformIO/Arduino)
- `/hardware`: CAD files, STLs for 3D printing, and detailed specifications
- `/resources`: Datasheets, component images, and 3D reference models
- `/software`: Python-side control, Computer Vision, and AI integration
- `/docs`: Technical documentation, kinematics calculations, and diagrams
- `tasks.md`: Detailed project roadmap and progress tracking

## Resources
- **ESP32-S3 Datasheet**: [Espressif Systems](https://www.espressif.com/sites/default/files/documentation/esp32-s3_datasheet_en.pdf)
- **MG996R Servo Reference**: [TowerPro MG996R Datasheet](https://www.towerpro.com.tw/product/mg996r/) / See `/resources/mg996r servo` for 3D models (STEP/SLDPRT)
- **Power Components**: 
  - [XL4016 Buck Converter Datasheet](https://www.xlsemi.com/datasheet/XL4016%20datasheet.pdf)
  - [MP1584EN Buck Converter Datasheet](https://www.monolithicpower.com/en/documentview/productdocument/dataset/document_id/510/pn/MP1584/)

## Getting Started
1. **Hardware**: Print parts from `/hardware` and assemble.
2. **Firmware**: Open `/firmware` in VS Code with PlatformIO and upload to ESP32.
3. **Control**: Open the serial monitor to send commands.
