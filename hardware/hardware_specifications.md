# Power Distribution & Hardware Plan

## System Overview
The system uses a 12V 10A SMPS as the primary power source, which is then stepped down to two different voltages to power the servos and the microcontroller separately.

## Power Components
1. **Primary PSU**: 12V 10A SMPS
2. **Servo Power (6V-7.2V)**: 
   - **Module**: XH-M404 (XL4016 based)
   - **Spec**: 250W 8A Adjustable Buck Converter
   - **Target Voltage**: Set to 6.6V - 7.2V for maximum torque from MG996R servos.
3. **ESP32 Power (5V)**:
   - **Module**: Mini MP1584EN DC-DC Buck
   - **Spec**: 3A max (peak)
   - **Target Voltage**: Set to 5V (connected to VIN/5V pin of ESP32).

## Microcontroller: ESP32 S3-WROOM-1
- **Operating Voltage**: 3.3V (Internal) / 5V (VIN)
- **Features**: Dual-core, WiFi/BT, enough GPIOs for multiple PWM and Analog inputs.

## Actuators: MG996R Analog Feedback Servos
- These servos have 4 wires:
  - **Red**: VCC (6V-7.2V)
  - **Black/Brown**: GND
  - **Yellow/Orange**: PWM Signal
  - **White/Green (Extra)**: Analog Feedback (Potentiometer wiper)

## Preliminary Pinout Plan (ESP32 S3)
| Component | Function | ESP32 S3 Pin (Proposed) |
|-----------|----------|-------------------------|
| Base Servo | PWM Signal | GPIO 4 |
| Base Servo | Feedback | GPIO 1 (ADC1_CH0) |
| Link 1 Servo | PWM Signal | GPIO 5 |
| Link 1 Servo | Feedback | GPIO 2 (ADC1_CH1) |
| Link 2 Servo | PWM Signal | GPIO 6 |
| Link 2 Servo | Feedback | GPIO 3 (ADC1_CH2) |
| Gripper Servo | PWM Signal | GPIO 7 |
| Gripper Servo | Feedback | GPIO 8 (ADC1_CH7) |
| Current Sensor | Analog In | GPIO 9 (ADC1_CH8) |

---
*Note: ESP32 S3 pins should be verified against the specific development board layout.*
