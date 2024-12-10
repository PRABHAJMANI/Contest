## Project SpiderBot

This repository contains the electronics and ROS-based work on Project SpiderBot developed during college. The focus was on integrating hardware components with a robust software stack to control a hexapod robotic platform.

## Electronics

- **Key Components**:
  - **Servos**: 35kg-cm (RKI 1202) and 16kg-cm (RKI 1206).
  - **Power Supply**: 4200mAh LiPo battery.
  - **Controllers**: Raspberry Pi 4 and Arduino Mega.
  - **Miscellaneous**: Single pole MCB, 10A buck converter, 10awg wires.
- **PCB Design**:
  - Trace widths: 188.89mils, 13.79mils, 6mils.
  - Copper weight: 2oz, Current rating: 20A.
  - Components: Arduino, Male-Male headers, XT-60 connector.

## Software (ROS Integration)

- **Framework**: ROS (Robot Operating System) was used to control the SpiderBot with Python as the primary language.
- **Communication**: ROSSerial protocol enabled communication between Raspberry Pi and Arduino.

### ROSSerial Setup

1. Install ROS and create a workspace.
2. Install ROSSerial packages:
   ```bash
   sudo apt-get install ros-<distro>-rosserial-arduino
   sudo apt-get install ros-<distro>-rosserial-python
   ```
3. Configure the Arduino code with ROSSerial headers and set communication parameters.
4. Run the ROSSerial node on the computer:
   ```bash
   rosrun rosserial_python serial_node.py /dev/ttyUSB0
   ```
5. Upload the Arduino code to the board.

## Running the Code

To start the SpiderBot, execute:

```bash
roslaunch spiderbot arduino.launch
roslaunch automation automation.launch
```
