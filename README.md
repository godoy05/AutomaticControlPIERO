# ESP32-Based Autonomous Vehicle Control System

## Overview
This project implements a real-time control system for a small autonomous vehicle using an ESP32. It focuses on applying feedback control to a physical system, where sensor data is used to continuously adjust the motor input and achieve stable behaviour.

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
- C/C++   
- PWM motor control  
- Control systems (PI/PID)  

## Context
This project was developed as part of a control systems course, with the goal of bridging theory and real-world implementation on embedded systems.

## Author
José Carlos Godoy Salvatierra

## Results

### Position Control - Left Response
![Left Graph](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/0caf7bf5-7be3-4971-b36d-815584cb8f18)

### Position Control - Right Response
![Right Graph](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/28ec579c-47b0-40db-af56-182f38e8af95)
