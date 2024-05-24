# canDrive

## Overview

Welcome to canDrive, the avant-garde toolkit engineered for the sophisticated hacking and comprehensive reverse engineering of your vehicle's Controller Area Network (CAN) system. This expansive project encapsulates a suite of components including Arduino-based software, a Python-driven graphical user interface (GUI), meticulously designed hardware schematics, and robust firmware for bespoke OBD2 modules. Navigate through our extensive tutorials to harness the full potential of each project component.

## Hacking Controller Area Network (CAN Bus)

### What is a Controller Area Network (CAN Bus)?

In short, it’s a communication system made for vehicle intercommunication. It is a network protocol commonly used in automobiles to allow different electronic components within the vehicle to communicate with each other over a shared two-wire bus. However, CAN is also used in a wide range of other industrial and commercial applications beyond just automobiles.

### Controller Area Network (CAN) Hacking

Controller Area Network (CAN) hacking involves exploiting vulnerabilities in the CAN bus network, which is a communication protocol used in vehicles and other industrial systems to allow different electronic components to communicate with each other. Ethical hackers utilize platforms like HackerOne to engage with security researchers to identify and fix security vulnerabilities in their products and systems.

### How to Hack CAN Bus?

To perform a CAN bus hack through HackerOne, an ethical hacker would typically follow these steps:

#### 1. Reconnaissance

The hacker gathers information about the target system, such as the make and model of the vehicle or industrial system, the firmware and software versions, and any other details that could be used to identify potential vulnerabilities.

#### 2. Vulnerability Scanning

Using specialized tools and techniques, the hacker scans the target system for known vulnerabilities and weaknesses in the CAN bus network. This could include looking for unsecured communication channels, weak encryption or authentication mechanisms, or other flaws in the network architecture.

#### 3. Exploitation

Once a vulnerability in the CAN bus network is identified, the hacker attempts to exploit it to gain access to the target system. This could involve injecting malicious code into the network, exploiting a buffer overflow or other memory-related vulnerability, or using other techniques to bypass security controls and gain control of the system.

#### 4. Post-exploitation

After gaining access to the target system, the hacker explores the system to identify additional vulnerabilities or sensitive information that could be leveraged for further attacks. This could include stealing data, escalating privileges, or installing backdoors or other malware to maintain persistence on the system.

Explore our comprehensive guides and tutorials to learn more about each step and how to effectively hack and reverse engineer CAN bus systems with canDrive.

## Contents

1. **canSniffer_Arduino**: Execute this Arduino script to establish a bidirectional communication channel between the automotive CAN bus and the GUI.
2. **canSniffer_GUI**: Leverage this advanced Python-based GUI application for the analytical reverse engineering of CAN packets.
3. **canSniffer_HW**: Explore the Altium Designer-created hardware schematics for our custom OBD2 module.
4. **canSniffer_FW**: Deploy this embedded firmware on the custom OBD2 module to facilitate real-time CAN packet processing.

## Detailed Descriptions

### 1. canSniffer_Arduino

The `canSniffer_Arduino` script is instrumental in bridging your vehicle's CAN interface with the `canSniffer_GUI` application. This script can be configured to either simulate CAN packets for developmental testing or to manage authentic CAN packet transmission and reception based on real-time automotive data.

**Key Features:**
- Seamless interface linkage between automotive CAN systems and GUI applications.
- Configurable CAN packet simulation for robust system testing (`RANDOM_CAN` flag).
- Dynamic handling of authentic CAN packet flows, adjustable to various CAN bus speeds (`CAN_SPEED`).

**Required Arduino Libraries:**
- CAN by Sandeep Mistry

**Essential Modifications:**
- **MCP2515.h**: Modify the clock frequency parameter from 16MHz to 8MHz to align with your MCP2515 setup.
- **MCP2515.cpp**: Expand the `CNF_MAPPER` to support your desired CAN bus speeds.

### 2. canSniffer_GUI

The `canSniffer_GUI` is a powerful Python-based application, crafted using PyQt. It is engineered to facilitate the intricate process of CAN packet reverse engineering by providing a user-friendly and visually intuitive interface.

**System Requirements:**
- Python 3.8 or higher
- Installation of necessary Python packages:
```sh
  $ pip install -r requirements.txt
```

# canDrive Project Documentation

## Included Files Overview

This repository houses the `save/decodedPackets.csv` file, which contains meticulously decoded packets vital for analyzing vehicle CAN bus data.

## canSniffer Hardware Design (`canSniffer_HW`)

### Overview

The `canSniffer_HW` section details the custom OBD2 module hardware projects engineered using Altium Designer. This includes comprehensive design files for two distinct PCB designs referred to as board1 and board2.

### Board Layout Images

#### Board1 - Top and Bottom Views
<img width="1018" alt="Screenshot 2024-05-24 at 4 48 53 PM" src="https://github.com/vm32/CAN-HWH/assets/21219411/d1548254-9687-42e3-bcfb-799afcaa2a0d">
<img width="1018" alt="Screenshot 2024-05-24 at 4 49 09 PM" src="https://github.com/vm32/CAN-HWH/assets/21219411/e2968322-c6ca-4a10-9e74-2afd1f920fac">

#### Board2 - Top and Bottom Views
<img width="1018" alt="Screenshot 2024-05-24 at 4 53 27 PM" src="https://github.com/vm32/CAN-HWH/assets/21219411/162ad6fe-616f-45c8-9a00-97eb23bad021">
<img width="1018" alt="Screenshot 2024-05-24 at 4 53 33 PM" src="https://github.com/vm32/CAN-HWH/assets/21219411/be4ffc42-3c42-4baf-bd17-64da8797c798">

### Key Resources

- Altium Designer project files.
- Component libraries hosted in a shared common folder.
- Schematic diagrams available in PDF format for enhanced accessibility.
- Future updates will include all PCB data.

## Firmware Development (`canSniffer_FW`)

### Current Developments

The `canSniffer_FW` directory contains the beta firmware for board1, developed utilizing STM32CubeIDE tailored for the STM32F413 microcontroller.

### Planned Updates

- Final firmware releases for both hardware boards.
- Development of firmware for board2, integrating nRF project capabilities.
- Source code for a new mobile application ensuring compatibility with version 2 hardware.
- Introduction of new hardware module versions to enhance functionality.

## Arduino CAN Library

This section introduces the Arduino CAN library, a versatile tool for interfacing with CAN networks via compatible hardware.

### Supported Hardware

- **Microchip MCP2515-based boards/shields**
- **Arduino MKR CAN shield**
- **Espressif ESP32**: Incorporates a built-in SJA1000 compatible CAN controller with an external 3.3V CAN transceiver.

#### Connection Specifications for Microchip MCP2515 and Espressif ESP32

| Device Component   | Connection | Pin |
|---------------------|------------|-----|
| **Microchip MCP2515** |            |     |
| VCC                 | 5V         |     |
| GND                 | GND        |     |
| SCK                 | SCK        |     |
| SO                  | MISO       |     |
| SI                  | MOSI       |     |
| CS                  | 10         |     |
| INT                 | 2          |     |

| **Espressif ESP32** |              |       |
|---------------------|--------------|-------|
| CAN transceiver     | ESP32        | Pins  |
| 3V3                 | 3V3          |       |
| GND                 | GND          |       |
| CTX                 | GPIO_5       |       |
| CRX                 | GPIO_4       |       |

### Installation Methods

#### Via Arduino IDE Library Manager
1. Navigate to `Sketch -> Include Library -> Manage Libraries...`
2. Search for "CAN"
3. Select the library and click `Install`.

#### Using Git
```sh
cd ~/Documents/Arduino/libraries/
git clone https://github.com/sandeepmistry/arduino-CAN CAN
```
## CSV Data

| Function             | ID (hex) | RTR (hex) | IDE (hex) | DLC (hex) | D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 | Notes                                      |
|----------------------|----------|-----------|-----------|-----------|----|----|----|----|----|----|----|----|--------------------------------------------|
| HS                   |          |           |           |           |    |    |    |    |    |    |    |    |                                            |
| Unknown              | 4EC      | 0         | 0         | 8         | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | Always at zero                             |
| Unknown              | 192      | 0         | 0         | 8         | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | Always at zero                             |
| Unknown              | 215      | 0         | 0         | 8         | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | Always at zero                             |
| Unknown              | 240      | 0         | 0         | 8         | 5  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | D0 changes between 04-07, others at zero  |
| Unknown              | 228      | 0         | 0         | 8         | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | Always at zero                             |
| Unknown              | 190      | 0         | 0         | 8         | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | Always at zero                             |
| Unknown              | 205      | 0         | 0         | 8         | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | Always at zero                             |
| Unknown              | 340      | 0         | 0         | 8         | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 0  | Always at zero                             |
| Unknown              | 4F1      | 0         | 0         | 8         | 41 | 1  | 9A | FF | FF | 64 | 5D | 5D |                                            |
| MS                   |          |           |           |           |    |    |    |    |    |    |    |    |                                            |
| Engine RPMs          | 201      | 0         | 0         | 8         | 0  | 0  |    |    |    |    |    |    | D0 and D1 together in hex                  |
| Accelerator Position | 201      | 0         | 0         | 8         |    |    |    |    | 0  |    |    |    | Between 0 and 200 (C8 in hex)             |
| Range left           | 400      | 0         | 0         | 8         |    |    |    |    | 0  | 0  |    |    | In km                                      |

## Test Car Information

The canDrive project was tested on the following car:

| Car Model | Year | CAN Type     | Testing Duration | Notes                                    |
|-----------|------|--------------|------------------|------------------------------------------|
| Mazda6    | 2017 | High-Speed CAN (HS CAN) | 3 weeks           | The project was tested for stability and accuracy in decoding and transmitting CAN packets. |
