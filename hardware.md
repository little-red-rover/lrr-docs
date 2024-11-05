# Hardware Documentation

[Find the open source hardware project on GitHub](https://github.com/little-red-rover/lrr-hardware)

Little Red Rover's hardware design is influenced by the same core priorities as the rest of the project:

1. Make it affordable (under $150)
2. Make it reliable (so it can be used in a large class without issues)
3. Make it capable (enough to be worth teaching a college course with)

These priorities, especially #1, played a major role in the design process.

## Off the Shelf Parts

Little Red Rover is a two wheel, differential drive mobile robot.
It consists of the following off the shelf parts:


## Electrical Design

### The circuit board

In recent years, custom printed circuit boards (PCBs) have become affordable enough for small batch production.
Little Red Rover's PCB is designed to be manufactured and assembled affordably, arriving fully functional on your doorstep, no soldering required.

Circuit boards can also be ordered with arbitrary outlines, making it possible to use them as mechanical parts.
LRR uses its circuit board as the main body of the robot, saving on parts count and helping with strength.

### Schematic

<kicanvas-embed src="https://raw.githubusercontent.com/little-red-rover/lrr-hardware/refs/heads/main/little_red_rover/little_red_rover.kicad_sch" controls="full" theme="kicad"> </kicanvas-embed>

### Layout

<kicanvas-embed src="https://raw.githubusercontent.com/little-red-rover/lrr-hardware/refs/heads/main/little_red_rover/little_red_rover.kicad_pcb" controls="full" theme="kicad"> </kicanvas-embed>

### Microcontroller

Little Red Rover is based around the ESP32-S3-MINI system on a chip from EspressIf.
The S3 was chosen because it has wireless capability (Wi-Fi and BLE) out of the box, plenty of IO, and an extensively documented SDK. 

### Sensors

The rover includes the following sensors:

### Power system

Little Red Rover is powered by a single cell Lithium-ion battery.
Lithium batteries can be extremely dangerous if used improperly, so great care must be taken to ensure safety.

The first set of protections are built into the battery itself.
The rover uses a protected 18650 battery, which means the battery includes a circuit in its housing that provides under voltage, over voltage, and short circuit protection.

The second set of protections are provided by the BQ24072RGT IC.
This battery charger chip manages safely charging and discharging the battery.

## Mechanical Design

Holding all the parts together are 7 3D printed components, designed to be printed on a low-end hobby grade machine.


