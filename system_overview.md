# System Overview

Little Red Rover consists of four major components:
1. Hardware
    * The physical components that make up the rover.
2. Firmware
    * The software the runs on the microcontroller onboard the rover.
3. ROS Drivers
    * ROS code that facilitates communication between the host computer and the rover. 
4. Tooling
    * Tools support cross platform support for the Rover.

This page gives a high level overview of each component and how they interconnect.
Each of these components are descibed in detail on their own page.

## System Diagram

**TODO**

Everyone loves a good diagram.

## Hardware to Firmware Interconnect

An ESP32-S3 microcontroller is used to orchestrate the rover's functionality.
Heres what it controls, and how:

* Planar LiDAR scanner
    * Communicates over UART
* 6 degree of freedom IMU
    * Communicates over I2C
* Two DC motors
    * Controlled using PWM
* Wheel encoders
    * Pulses counted using the [ESP32 PCNT peripheral](https://docs.espressif.com/projects/esp-idf/en/v5.3.1/esp32/api-reference/peripherals/pcnt.html)
* Status LEDs
    * Controlled using the [ESP32 RMT peripheral](https://docs.espressif.com/projects/esp-idf/en/v5.3.1/esp32/api-reference/peripherals/rmt.html)

Commands and sensor data are exchanged over wifi, as descibed in the following section.

## Firmware to ROS Interconnect

The ESP32 onboard the rover is wifi capable.
To communicate with the host computer, the ESP32 starts an wifi access point (think hotspot).
When the host computer connects to the rover access point, the firmware logs the relevant IP and opens a UDP socket with that IP on port 8001.

Sensor data from the robot is serialized (turned a language neuteral binary format) using [Protocol Buffers](https://protobuf.dev/).
Specifically, the firmware side serialization uses [nanopb](https://github.com/nanopb/nanopb) to serialize it's c data structures.
The serialized data is sent over the UDP port, where it is unpacked in Python using the `protobuf` package.
Commands from ROS are communicated the same way, just in the inverse direction.

Within ROS, messages are interpreted by the hardware abstraction layer (HAL).
The HAL is a node that serves as a translator between ROS messages and Protocal Buffer messages.
For outgoing messages, it subscribes to all topics relevant to the robot, repackages any incoming data into a buffer, then sends the message over UDP.
For incoming data it listens on the UDP port for messages from the rover, then unpacks the data and publishes it as a ROS message on the relevant topic.

> [!NOTE]
> The hardware abstraction layer is currently implemented as a python ROS node.
> The idiomatic, ROS-y way to handle this problem is implementing a hardware controller using [ros_control](https://wiki.ros.org/ros_control).
> This improvement is tracked in an issue on the [ros driver's github](https://github.com/little-red-rover/lrr-ros/issues/2).

## ROS to User Interconnect

The offical advice for getting started with ROS is to first install Linux. This is where many people's ROS journey started and ended.

Little Red Rover is built for begginers, so this was an unacceptably obtuse solution.
Instead, the project provideds a containerized development environment through [Docker](https://www.docker.com/) and [DevContainers](https://containers.dev/).

Docker provides a container runtime - a piece of software that allows you to run portable and self contained software applications.
Portable means they will run on any host OS, and self contained means they contain all dependencies of the software (including the OS!).

DevContainers provide utilities for using containers not only to run software, but also to develop it.
Notably, DevContainers are integrated into VSCode to provide a one button solution for launching a containerized developement environment.

It is difficult to run graphical apps from within a Docker container, so we leverage web based visualization tools.
The best of which is, in my opinion, [Foxglove](https://foxglove.dev).
Foxglove communicates with ROS using a websocket connection, allowing the user to visualize the robot and its data in real time.
