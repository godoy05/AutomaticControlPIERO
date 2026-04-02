## Dead Zone and Saturation Analysis

In this section, the dead zone and saturation of the system are studied. A data acquisition model ("toma_datos") is used to determine both effects.

The "toma_datos" model is composed of the PIERO_HW subsystem, which includes two main components: the motors subsystem and the encoder.

## PIERO_HW Model

<img width="947" height="347" alt="1" src="https://github.com/user-attachments/assets/7736024c-a866-4a50-b064-0462dfef8b84" />

This model represents the hardware of the system, including the motors and the encoder, which are responsible for actuation and measurement.

## Motors Model

This model represents the behavior of the motors, including their dynamic response to input signals.

<img width="790" height="537" alt="2" src="https://github.com/user-attachments/assets/a9902160-a16e-48f3-ba45-8f4035c6e7e6" />


## Encoder Model

This model represents the encoder used to measure the wheel velocities, providing feedback for the control system.

<img width="920" height="455" alt="3" src="https://github.com/user-attachments/assets/6879b805-7ace-4d44-a365-8074cff9fcde" />


## Data Acquisition Model (Toma Datos)

This model is used to collect system data, combining the hardware components to analyze the system response and identify key characteristics such as dead zone and saturation.

<img width="1157" height="382" alt="4" src="https://github.com/user-attachments/assets/b5e2ad30-4aef-4600-a179-974d08e9440e" />


## Ramp Input Signal

A ramp signal is used as input to evaluate the system behavior, allowing the observation of dead zone and saturation effects.

<img width="1073" height="626" alt="5" src="https://github.com/user-attachments/assets/c14153cb-a2f4-47a2-a8b1-3b8c3f8f01a1" />


## Scope and Data Table

From the scope, a delay in the system response can be observed, along with two saturation peaks (both positive and negative) and a small inertia at the end of the response.

<img width="886" height="265" alt="6" src="https://github.com/user-attachments/assets/94501066-f447-482b-9e45-ef08be359d37" />


The following table shows the data obtained from the experiment.

<img width="1000" height="423" alt="7" src="https://github.com/user-attachments/assets/00e2ce11-e7de-47c1-8746-4ce6afe47e25" />


## Dead Zone Determination Video

The demo video is available in this folder as "dead_zone_and_saturation_identification_demo.mp4" and can be downloaded.

## Open-Loop Control

The open-loop control system makes use of the previously defined PIERO_HW model, together with a new subsystem called ControlBA.

## ControlBA

The ControlBA subsystem uses two blocks called "Lookup with Linear Lagrange Interpolation", one for each wheel (left and right).

To configure these blocks, open the block settings and select "Edit table and breakpoints". Then, input the values obtained from the data table, ranging from -255 to 255.

<img width="1112" height="358" alt="8" src="https://github.com/user-attachments/assets/61ca9e20-4f91-4fe2-bfd8-951b4b5d8f24" />


## Right Wheel

This block defines the control input for the right wheel based on the interpolation of the experimental data.

<img width="1121" height="661" alt="9" src="https://github.com/user-attachments/assets/3525085a-9788-4373-ad2d-21482ecdb943" />


## Left Wheel

This block defines the control input for the left wheel using the same interpolation approach.

<img width="1122" height="630" alt="10" src="https://github.com/user-attachments/assets/cbf1abc0-c18b-46c9-a27f-f9987303929b" />


## Data Extraction for System Identification Using a Pulse Input

To extract the data required for system identification, the "toma_datos" model is used again, this time with a pulse input signal.

## Data Acquisition Model

This model is used to collect the system response data under the pulse excitation.

<img width="1192" height="591" alt="11" src="https://github.com/user-attachments/assets/fb10c4be-eaa7-49e5-907c-1ed4efb58ac6" />


## Pulse Input Signal

A pulse signal is applied to excite the system and capture its dynamic response.

<img width="1073" height="621" alt="12" src="https://github.com/user-attachments/assets/971b71f8-6615-4d31-aa7c-05550366d721" />


## Scope Visualization

The system response can be observed in the scope, where the effect of the pulse input on the system output is shown.

<img width="886" height="659" alt="13" src="https://github.com/user-attachments/assets/21651a25-4db5-443d-9d47-fc97f0415e1d" />

## Square Wave Identification Video

The demo video showing the square wave identification process is available in this folder as "system_identification_process_demo.mp4" and can be downloaded.

As with the ramp input, the data is recorded in the same way.

## System identification ##

The collected data is imported in order to obtain the transfer function of the PIERO system.

<img width="847" height="540" alt="14" src="https://github.com/user-attachments/assets/d1516db5-1d10-418c-9dc6-45a09967a6eb" />

From this process, the transfer functions for both the left and right wheels are obtained. Different combinations of poles and zeros are tested to select the most suitable model.

In this case, a model with one pole and no zeros was selected for both wheels, as it provided the lowest error. The response was also adjusted to reduce the final inertia observed in the system.

## Right Wheel Transfer Function

This section shows the identified transfer function for the right wheel.

<img width="470" height="472" alt="15" src="https://github.com/user-attachments/assets/221f55e5-ea3a-47ff-90d0-9eeb1efa09a0" />


## Left Wheel Transfer Function

This section shows the identified transfer function for the left wheel.

<img width="357" height="383" alt="16" src="https://github.com/user-attachments/assets/034c10be-a951-464e-9350-205ce439c714" />


## Digital Twin

Finally, the digital twin of the system is developed.

<img width="1006" height="482" alt="17" src="https://github.com/user-attachments/assets/9ffc47e7-9265-4b3e-81ca-32e204b7903e" />

This model includes the Piero_Model subsystem, where the transfer functions obtained for both wheels are implemented.

<img width="1037" height="467" alt="19" src="https://github.com/user-attachments/assets/52146656-3598-4b47-b94f-8a7ba06ece62" />


















