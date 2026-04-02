## Conversion from continuous to discrete domain ##

We will work with discrete variables, so in order to reuse the previously developed subsystems, it is necessary to convert them from continuous to discrete form.

This milestone is divided into four parts:

# 1. H41_1 meter #

This section focuses on achieving a 1-meter displacement of the vehicle using closed-loop control. The system regulates the linear velocity to ensure accurate and stable motion over the desired distance.

<img width="1225" height="516" alt="H41_1 etro" src="https://github.com/user-attachments/assets/2e08785c-fd1e-4928-87cf-c96846c98042" />


The system is composed of three subsystems:

#  PieroControlled1mZ #

<img width="1220" height="515" alt="2" src="https://github.com/user-attachments/assets/b81bf38c-962e-4397-af24-4de7163a350f" />

Each of them is further composed of two subsystems:

# -ControllerPosition1mZ #

<img width="1291" height="467" alt="3" src="https://github.com/user-attachments/assets/a2709ccf-e84c-4896-9eac-2d23e9dea57d" />

In this part, the PID controller must be converted from continuous to discrete form. Once this is done, the required conditions are applied to each of the two wheels.

- Synchronized PID controller for the left wheel:
  
<img width="1318" height="811" alt="4" src="https://github.com/user-attachments/assets/276142f0-837d-4337-bc1d-a7fef9defc87" />

- Synchronized PID controller for the right wheel:
<img width="1537" height="797" alt="5" src="https://github.com/user-attachments/assets/f0a1bc59-9d77-4b57-9e16-3aab26d4bac5" />

# -DigitalTwinZ #

<img width="962" height="463" alt="6" src="https://github.com/user-attachments/assets/5e59f41d-b5a3-4f8e-997a-7414c5d47bf5" />

It is composed of two subsystems: the previously used PIEROJAJ_HW and Piero_ModelZ, where the system is modeled using its transfer function in the Z-domain.

<img width="997" height="372" alt="7" src="https://github.com/user-attachments/assets/28422a52-b3f9-4eba-a9af-0449e92c7ad2" />

The Z-domain transfer function is obtained following the same approach used in the continuous case. System Identification is used to select the model with the lowest error.

<img width="835" height="561" alt="8" src="https://github.com/user-attachments/assets/382d2380-428a-4384-b28b-183283eb61b0" />

- Transfer function of the left wheel:
<img width="297" height="463" alt="9" src="https://github.com/user-attachments/assets/914702ad-a5ba-4123-840a-7dace34c24b4" />

- Transfer function of the right wheel:
<img width="487" height="502" alt="10" src="https://github.com/user-attachments/assets/7585040e-a527-42ef-abd9-fd1d2b991730" />


# MCD #

The kinematic model is used to relate the wheel velocities to the motion of the vehicle. It allows computing the linear and angular movement of the robot based on the speed of each wheel.

<img width="672" height="358" alt="11" src="https://github.com/user-attachments/assets/e51ea442-18b0-4fa2-8333-63f917381921" />


# Odometry #

Odometry is used to estimate the position and orientation of the robot over time using the wheel velocities. It provides an approximation of the robot’s trajectory based on the kinematic model.

<img width="1078" height="621" alt="12" src="https://github.com/user-attachments/assets/82c1ad40-0438-4d5a-b69d-035665ad46f9" />

Where the deviation can be observed:

<img width="1146" height="721" alt="13" src="https://github.com/user-attachments/assets/40b9b6a6-4511-4899-8441-213eb1d65e22" />

# 2. H42_1Circle #

<img width="1632" height="608" alt="14" src="https://github.com/user-attachments/assets/b7351b4f-1132-47d5-8293-002d84102d58" />

It is composed of the three subsystems previously used in H41_1 meter, but now an additional external PID controller is introduced, which must be tuned.

- Plot of the angular velocity controller meeting the specifications:

<img width="1325" height="807" alt="15" src="https://github.com/user-attachments/assets/b2d721bb-c855-4e19-9d89-83518a264674" />

<img width="325" height="265" alt="16" src="https://github.com/user-attachments/assets/f0bddd24-7548-482a-8684-bf503cd63a60" />

# 3. H43_Rotation360 #

This section focuses on achieving a 360-degree rotation of the vehicle using closed-loop control. The angular motion is regulated by a PID controller to ensure accurate and stable behavior.

<img width="1256" height="527" alt="17" src="https://github.com/user-attachments/assets/d4dcd149-bd13-4770-b287-4f3a875233da" />


Odometría:

<img width="1117" height="652" alt="18" src="https://github.com/user-attachments/assets/6d513ced-0ead-4fd2-a8e8-741b56f05894" />


# 4. H4_ExitRoom#

This section focuses on the vehicle exiting the classroom using closed-loop control. The objective is to guide the robot along a defined path while maintaining stable and accurate motion.

<img width="1637" height="597" alt="19" src="https://github.com/user-attachments/assets/d52f6952-76f8-4871-93d3-94dd8aa8f6e9" />

Two input signals are used: one for the linear velocity and another for the steering angle.

- Linear velocity signal (V):

Señal para la velociad de giro (Theta):

<img width="715" height="617" alt="20" src="https://github.com/user-attachments/assets/ebd63a11-b35d-4853-b3b4-dcaa7623f7da" />

- Odometry

<img width="703" height="625" alt="21" src="https://github.com/user-attachments/assets/08477cd6-24af-4909-a01a-2698e0f7a2c8" />




























