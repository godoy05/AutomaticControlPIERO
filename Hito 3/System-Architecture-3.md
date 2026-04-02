## Continuous Control (Closed-Loop) ##

This block is composed of the "Digital Twin" subsystem and a new subsystem called "ControlBC".

<img width="1473" height="547" alt="1" src="https://github.com/user-attachments/assets/6ea53f6b-20c6-4c61-9533-afafc5712e9b" />


# ControlBC # 

This subsystem is composed of two PID controllers, which must be tuned according to the required specifications. Each controller is responsible for regulating the system to achieve the desired performance.

<img width="1183" height="451" alt="2" src="https://github.com/user-attachments/assets/8863a46f-f509-4f9b-990c-721eba03c29a" />

- Synchronized PID Controller for the Left Wheel

<img width="1282" height="853" alt="3" src="https://github.com/user-attachments/assets/6491a4df-2dfd-44a3-bf0f-678f1a2263b2" />

- Synchronized PID Controller for the Right Wheel

<img width="1283" height="807" alt="4" src="https://github.com/user-attachments/assets/08ce946d-670f-43c7-948e-958ac182f8a2" />

## Trajectory Correction Video

The demo video can be found in this folder as "disturbance_rejection_demo.mp4" and is available for download.

## Kinematic Test ##

<img width="1796" height="592" alt="5" src="https://github.com/user-attachments/assets/c326d3aa-73ec-40f4-8307-70bdfa286adc" />

The kinematic test is composed of four main subsystems, each responsible for a different aspect of the vehicle’s motion and behavior. Together, they allow modeling, controlling, and evaluating the robot’s trajectory.

# MCI (Inverse Kinematic Model)#

This subsystem computes the required wheel velocities from the desired linear and angular motion of the vehicle.

<img width="575" height="362" alt="6" src="https://github.com/user-attachments/assets/eb697c85-53d9-4d04-9283-e4fd8075f3dc" />


# MCD (Direct Kinematic Model)#

This subsystem calculates the vehicle’s motion based on the wheel velocities, providing the resulting linear and angular displacement.

<img width="641" height="381" alt="7" src="https://github.com/user-attachments/assets/c7f56714-280c-4f4a-afd4-10080fa605fa" />


# Controlled PIERO #

This block represents the controlled system, where the implemented controllers regulate the behavior of the vehicle.

<img width="1167" height="551" alt="8" src="https://github.com/user-attachments/assets/c0c694f2-b57d-45ef-a0ea-0ed4c00ed8ee" />

# Odometry #

This subsystem is used to estimate and visualize the trajectory of the robot over time based on its motion.

![image](https://github.com/Escuela-de-Ingenierias-Industriales/RegulacionAutomatica23-godoy05/assets/145486537/17030a93-4ae6-4dfa-a1a7-188257ff4fa0)

Within the odometry subsystem, the XY plot can be observed, showing the trajectory of the vehicle.

<img width="1007" height="575" alt="9" src="https://github.com/user-attachments/assets/d447899b-98ec-4a18-b20c-9a703473272a" />


# DEMO Video

The demo video is available in this folder as "vehicle_trajectory_demo.mp4" and can be downloaded.











