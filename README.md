# Soil-moisture-detection
A soil moisture monitoring system using an STM32F4 microcontroller. It reads moisture levels via an ADC-connected sensor, indicates moisture status with LEDs, and conserves power by controlling sensor power. The readings are periodically sent to a Bluetooth-enabled device for remote monitoring.
Project Overview
This project is a soil moisture monitoring system built using an STM32F4 microcontroller. The system reads soil moisture levels through an analog sensor connected to an ADC channel. Based on the moisture levels, it illuminates one of three LEDs to indicate the soil moisture status: high, medium, or low. The sensor is powered only during measurements to conserve energy. The moisture level readings are periodically transmitted to a Bluetooth-enabled device, allowing for remote monitoring of soil conditions.

Features
Soil Moisture Sensing: Uses an analog soil moisture sensor connected to the ADC.
LED Indication: Three LEDs (Red, Green, and Blue) indicate high, medium, or low moisture levels.
Bluetooth Communication: Moisture readings are sent via Bluetooth to a connected device every 10 seconds.
Energy Efficient: Controls sensor power to reduce energy consumption when not in use.
Hardware Requirements
STM32F4 microcontroller
Soil moisture sensor
HC-05 Bluetooth module
LEDs (Red, Green, Blue)
Resistors and connecting wires
Software Requirements
Keil uVision IDE (Version 5 or later)
STM32CubeMX (for clock and peripheral configuration, optional)
Circuit Configuration
Moisture Sensor: Connected to ADC channel PA7
LEDs:
Red LED: PA5 (indicates high moisture)
Green LED: PA3 (indicates medium moisture)
Blue LED: PA1 (indicates low moisture)
Sensor Power: PB1 (controls sensor power supply)
Bluetooth Module: USART1 (PA9 for TX, PA10 for RX)
Code Functionality
System Initialization: Configures the system clock, GPIOs, UART, ADC, and Timer.
ADC Reading: Reads the analog input from the moisture sensor and categorizes it into three levels.
LED Control: Activates the appropriate LED based on the moisture level.
Bluetooth Transmission: Sends the moisture level data to a Bluetooth-connected device every 10 seconds.
Power Management: Powers the sensor only during ADC readings to conserve energy
