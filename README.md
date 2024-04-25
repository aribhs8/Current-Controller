# Current Controller
An embedded circuit powered by the ATTINY85 MCU. The device uses a series-parallel resistor network with a few transistors to control the flow of current through a specific resistance path, outputting a desired current. The user must specify the correct voltage (1.8V, 3.3V or 5V) to properly determine the correct current.

## 🤔 Motivation
When testing electronics, occasionally the need arises to pass through a specific current to a device. Usually, a tester may want to do this for one of the following reasons:
1. Safety
    - Prevent damage to device under test and testing equipment.
    - Ensure device operates within safe operating limits (avoid overloading and/or overheating)
2. Accuracy
    - Accurately measure device's characteristics (impedance, V-I curves, etc.).
    - Useful for characterizing electronic components.
3. Analysis
    - See how device responds under different operating conditions.
4. Calibration
    - Calibration of testing equipment or device to check measurements.
5. Fault Detection
    - See how current affects operation of device; watch for excessive power consumption, leakage or unexpected voltage drops.

### 🏁 Goal
The goal of this device was to help electronic testers accomplish these different current tests. The device allows the user to output a specific current given information about the desired value and the voltage being passed through.

## ⚙️ Additional Specifications
To control the flow of current, an nxn series-parallel network of resistors was created with a set of MOSFETS to control the flow each resistor by row and column. The ATTINY85 MCU was used to control the entire circuit. The MCU's operations include the following:
- Reading value from 3-way switch about voltage (1.8V, 3.3V, 5V)
- Controlling each MOSFET to direct curret path
- Read input from button indicating desired current
- Control matrix of LEDs to indicate selected current

## 🚀 Quick Start
A PDF file can be found in the Current_Controller directory displaying the overall circuit schematic. The schematic and PCB were created in Altium Designer. The project can be imported into this program to edit the overall schematic or PCB.

## 🚴 Usage
To utilize this circuit, you will need the components found in the BOM file. The PCB must also be fabricated and then the components soldered onto the board. After soldering these components, you can upload the MCU FW onto the device.

Power the device through the PWR header using a voltage of 3.3V. Then place the device between two terminals. Specify the target current and watch as the device produces the desired current for you. You can validate using an ammeter.