# ESP32-Based Autonomous Vehicle Control System

## Overview
This project implements a real-time embedded control system for an autonomous vehicle using an ESP32. It focuses on applying feedback control to a physical system, where sensor data is continuously processed to regulate motor input and achieve stable and accurate behavior.

The system is designed around a closed-loop architecture, where the vehicle measures its current state (such as speed, distance, or position), compares it to a desired reference, and corrects the error using a digital controller.

## How it works
The ESP32 runs a control loop that:
1. Reads data from sensors  
2. Computes the error between the reference and the measured value  
3. Applies a control law (PI/PID)  
4. Updates the motor speed using PWM  

This loop runs continuously to ensure the system reacts in real time to changes in the environment.

## Key aspects
- Real-time control implemented on embedded hardware  
- Closed-loop feedback system  
- PI/PID controller implementation and tuning  
- Sensor integration and signal handling  
- Motor control using PWM  

## Technologies
- ESP32     
- PWM motor control  
- Control systems (PI/PID)  

## System Architecture
The system is organized into sensing, control, and actuation layers. Sensor data is processed in real time, a control algorithm (PI/PID) computes the required action, and PWM signals are applied to the motors to achieve the desired behavior.

## Experiments
The system was tested in several scenarios to validate its performance:

- 1 meter position control  
- 360° rotation  
- Circular trajectory tracking  
- Classroom exit trajectory  
- Disturbance rejection  

These experiments demonstrate the effectiveness of the control system under different operating conditions.

## Demo
Demo videos are available in the corresponding folders of the repository, where each experiment includes its own demonstration.

## Author
José Carlos Godoy Salvatierra


