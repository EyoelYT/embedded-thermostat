# Embedded-Thermostat

## Project Overview

The Embedded-Thermostat project is a temperature control system designed to maintain a specified temperature set-point within an environment. The system integrates multiple peripherals on a Texas Instruments (TI) microcontroller to read temperature data from a sensor, adjust the set-point via button inputs, control an LED to indicate heating status, and communicate system status to an external server via UART.

## Features

- **Temperature Monitoring**: Continuously reads the current temperature from a sensor using I2C communication.
- **Set-Point Adjustment**: Allows users to increase or decrease the temperature set-point using button inputs.
- **Heating Control**: Controls an LED to indicate the heating status based on the current temperature relative to the set-point.
- **Real-Time Communication**: Sends system status updates to an external server via UART in a specified format.
- **Modular Design**: Structured to enhance maintainability, readability, and adaptability.

## System Components

### Hardware

- **Microcontroller**: Texas Instruments (TI) CC3220S
- **Temperature Sensor**: I2C-based temperature sensor
- **LED**: Indicating heating status
- **Buttons**: For set-point adjustment

### Software

- **Programming Language**: C
- **Development Environment**: TI Code Composer Studio
- **Real-Time Operating System**: TI-RTOS
- **Version Control**: Git

## Functionality

### Peripherals

- **UART**: Used for communication with an external server. Data is sent in the format `<AA,BB,S,CCCC>`, where:
  - `AA` is the room temperature (00-99) degrees Celsius.
  - `BB` is the set-point temperature (00-99) degrees Celsius.
  - `S` indicates the heating status (`0` for off, `1` for on).
  - `CCCC` is the count of seconds since the board was reset.

- **I2C**: Used to read data from the temperature sensor.
- **GPIO**: Used for button inputs and LED control.

### Timing and Scheduling

- **Button Check**: Every 200ms, the system checks the button inputs to adjust the set-point temperature.
- **Temperature Reading and LED Update**: Every 500ms, the system reads the temperature and updates the LED based on the heating status.
- **UART Update**: Every second, the system sends an update to the external server with the current status.

## Getting Started

### Prerequisites

- **Hardware**: TI CC3220S microcontroller, I2C temperature sensor, LED, buttons
- **Software**: TI Code Composer Studio, Git

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/embedded-thermostat.git
   ```
2. Open the project in TI Code Composer Studio.
3. Build and upload the firmware to the TI CC3220S microcontroller.

### Usage

1. Power on the microcontroller.
2. Adjust the temperature set-point using the buttons.
3. Open a COM port.
4. Monitor the LED to see the heating status.
5. View the status updates sent via UART to the external server.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

Texas Instruments for providing the microcontroller and development tools.
Open-source communities for their valuable resources and support.
