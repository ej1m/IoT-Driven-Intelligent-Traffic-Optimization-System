# IoT-Driven Intelligent Traffic Optimization System

This system provides a cost-effective and scalable solution for traffic management, offering enhanced energy efficiency, improved emergency vehicle access and better overall traffic regulation, making it particularly suitable for underdeveloped regions.  

Equipment Overview:  

The system is built around the ESP32 microcontroller, acting as the central processing hub and the SIM800L GSM module, which ensures real-time data communication with the cloud via the MQTT protocol. 

Power management is achieved through the LM2596 buck converter, stepping down voltage to power the ESP32, and the MT3608 boost converter, which provides optimal voltage for the SG90 servomotors.  

Sensors and Actuators: 

The system integrates HW-201 IR sensors to monitor lane-specific vehicle congestion, LDRs for automatic streetlight activation based on ambient light and LM393 sound sensors to detect emergency sirens. These inputs enable dynamic lane prioritization and energy-efficient streetlight control. 

Actuators include SG90 servomotors controlling lane blockades, 7-segment displays for countdown timers, and LEDs for traffic lights and streetlight management.  

Power Supply and Regulation:  

A 12V power source drives the system, with the buck converter providing 3.3V for the ESP32 and the boost converter supplying the SG90 servomotors with the required voltage for optimal operation.
  
Operation Logic:  

Sensor Data Processing: IR sensors collect congestion data, which is processed by the ESP32 to determine the densest lane. LDRs ensure energy efficiency by activating streetlights only under low-light conditions. Sound sensors detect emergency sirens, overriding normal lane prioritization to ensure swift passage for emergency vehicles.
  
Actuator Control: The ESP32 controls servomotors to open and close lane blockades dynamically. The system adjusts traffic lights and displays synchronized countdown timers to inform drivers of phase changes.

Traffic Lights and Streetlights: Traffic lights switch based on prioritization logic, while streetlights, controlled by LDRs, operate only when necessary to conserve energy.  

Communication and Data Management:  

All sensor data is transmitted to an MQTT server for logging and analysis. The SIM800L facilitates remote monitoring and real-time adjustments, ensuring the system remains adaptable to traffic changes and emergencies.  

Lane Prioritization Algorithm: 

The core algorithm prioritizes lanes with the highest congestion unless an emergency siren is detected. In such cases, the system immediately clears the relevant lane while maintaining smooth traffic flow in other areas.  

