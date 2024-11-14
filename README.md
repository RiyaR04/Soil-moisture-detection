
# Soil Moisture Monitoring System with STM32F4 and Bluetooth Communication

## Project Overview
This project implements a soil moisture monitoring system using an STM32F4 microcontroller. The system measures soil moisture levels with an analog sensor connected to an ADC channel, providing visual feedback through LEDs and sending data to a Bluetooth-enabled device for remote monitoring. The sensor power is controlled to conserve energy, and ADC readings are taken periodically and transmitted via Bluetooth.


https://github.com/user-attachments/assets/bf65b913-da0d-4557-be7b-4725e964e64d


## Features
- **Moisture Level Detection**: The system reads soil moisture levels using an analog soil moisture sensor.
- **LED Indicators**: Three LEDs indicate the soil moisture status:
  - **Red LED**: High moisture level
  - **Green LED**: Medium moisture level
  - **Blue LED**: Low moisture level
- **Bluetooth Communication**: The system sends moisture readings to a Bluetooth-enabled device for monitoring.
- **Power Management**: The sensor’s power is managed via GPIO to conserve energy.

## Hardware Setup
1. **STM32F4 Microcontroller**: Used for analog-to-digital conversion, LED indication, and Bluetooth communication.
2. **Soil Moisture Sensor**: Connected to an ADC channel (PA7).
3. **LEDs**: Three LEDs are connected to GPIO pins on PA1 (Blue), PA3 (Green), and PA5 (Red).
4. **HC-05 Bluetooth Module**: Used to transmit soil moisture readings.
5. **Power Control**: The sensor power is controlled using GPIO pin PB1.
![WhatsApp Image 2024-11-04 at 22 24 47_f458d119](https://github.com/user-attachments/assets/e964603d-317e-4550-ad0b-0ac4561f0cd7)

## Software Configuration
- **USART for Bluetooth**: Configured to communicate with the HC-05 module for data transmission.
- **ADC for Sensor Readings**: Configured to read soil moisture data from the sensor.
- **GPIO for LED Control**: Used to indicate different moisture levels based on ADC readings.
- **Timer (TIM2)**: Configured to trigger periodic sensor readings and data transmission every 10 seconds.

## Code Explanation
- **GPIO Initialization** (`GPIO_Init`): Configures GPIO pins for LED indicators, sensor power, and USART communication.
- **USART Initialization** (`USART1_Init`): Configures UART for Bluetooth communication with a baud rate of 9600.
- **ADC Initialization** (`ADC1_Init`): Sets up ADC for reading moisture sensor data on channel 7 (PA7).
- **Timer Initialization** (`TIM2_Init`): Sets up a timer interrupt to trigger ADC reading and data transmission every 10 seconds.
- **Moisture Level Processing**: The timer interrupt handler reads the ADC value, determines moisture level, updates LEDs, and sends the data over Bluetooth.
  
## Getting Started
1. **Compile and Upload**: Compile the code using Keil uVision or a compatible IDE and upload it to the STM32F4 board.
2. **Setup Hardware**: Connect the soil moisture sensor, LEDs, and HC-05 Bluetooth module as per the hardware setup.
3. **Monitor Output**: Use a Bluetooth serial app (e.g., Serial Bluetooth Terminal) to view moisture readings on a paired mobile device.

## Project Details
- **IDE**: Keil uVision (Version 5)
- **Microcontroller**: STM32F401RET6

## Acknowledgments
This project is part of the coursework for **[19CSE303: Embedded Systems]**.

### Team Members
CB.EN.U4CSE22425 Nair Divya Premchandrakumar  
CB.EN.U4CSE22434 Rohit Vishnu P  
CB.EN.U4CSE22435 Riya Rajesh  
CB.EN.U4CSE22460 Samyuktha BM

**Department of Computer Science and Engineering**  
Amrita School of Computing,  
Amrita Vishwa Vidyapeetham, Coimbatore, India.
