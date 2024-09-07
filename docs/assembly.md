# Kit Assembly

This tutorial will guide you through assembling your rover. It should take around 15 minutes.

## Bill Of Materials

First, make sure your kit has all the required materials.

![All parts](./_images/assembly/all_parts.webp)

In the box:

| Item | Quantity | Picture |
| ---- | ---- | ---- |
| Circuit board | 1 | ![Circuit board](./_images/assembly/circuit_board.webp) |
| LD-20 lidar  | 1 | ![Lidar](./_images/assembly/lidar.webp) |
| Orange wheels | 2 | ![Two orange wheels](./_images/assembly/wheels.webp) |
| Motor with encoder | 2 | ![Two motors](./_images/assembly/motors.webp) |
| 18650 LiIon battery, 5000 mah | 1 | ![18650 battery](./_images/assembly/battery.webp) |
| USB-C to C cable | 1 | ![USB C to C cable](./_images/assembly/usb_cable.webp) |
| Front skid | 1 | ![Front skid](./_images/assembly/front_skid.webp) |
| Motor mount | 2 | ![Motor mounts](./_images/assembly/motor_mounts.webp) |
| Cable bag | 1 | ![Cable bag](./_images/assembly/cable_bag.webp) |
| Small parts bag | 1 | ![Small parts bag](./_images/assembly/small_parts_bag.webp) |

In the cable bag:

| Item | Quantity | Picture |
| ---- | ---- | ---- |
| 4-pin JST GH 1.25mm straight across cable | 1 | ![Motor cables](./_images/assembly/motor_cables.webp) |
| 6-pin JST PH 2.0mm reversed cables | 2 | ![Lidar cable](./_images/assembly/lidar_cable.webp) |

In the small parts bag:

| Item | Quantity | Picture |
| ---- | ---- | ---- |
| Motor attachment shims | 2 | ![Motor attachment shims](./_images/assembly/motor_attachment_shims.webp) |
| Motor spacing shims | 2 | ![Motor spacing shims](./_images/assembly/motor_spacing_shims.webp) |
| Wheel spacers | 2 | ![Wheel spacers](./_images/assembly/wheel_spacers.webp) |
| M3-8 machine screw | 3 | ![Machine screws](./_images/assembly/bolts.webp) |
| M2.5 hex key | 1 | ![Hex key](./_images/assembly/hex_key.webp) |

## Motor Subassembly

Insert a motor cable into one of the motors. Note the ridges on the connector, it can only be installed in one orientation.

![Cable installed in a motor](./_images/assembly/cable_in_motor.webp)

Take a motor and place it in a motor mount.

![Motor in motor mount](./_images/assembly/motor_in_mount.webp)

Add a motor spacing shim on top of the motor.

![Motor with spacing shim installed](./_images/assembly/add_motor_shim.webp)

Repeat with the other motor, making sure the second assembly is mirrored to the first.

![Motor with spacing shim installed](./_images/assembly/both_motor_assemblies.webp)

## Body Assembly

At the base of the circuit board, there are cutouts for the motor mount to slot into place.
Insert the circuit board into the gap...

![Inserting the circuit board into the motor mount](./_images/assembly/before_mounting_motor.webp)

... then guide the other end of the motor mount up through the slots in the PCB.

![Guiding the mount up into the board](./_images/assembly/after_mounting_motor.webp)

Place a motor attachment shim over the parts of the motor mount exposed above the board.
Push the attachment shim up and into place, locking the motor into place.
The hole in the attachment shim should line up with the bolt hole in the circuit board.

<img alt='Attachment shim placed' src='./_images/assembly/attachment_shim_before.webp' width="52%"/>
<img alt='Attachment shim pushed up' src='./_images/assembly/attachment_shim_after.webp' width="47%"/>

Repeat with the other motor.

![Both motors attached to the board](./_images/assembly/both_motors_attached.webp)

Flip the robot over.
Insert the motor cables into their connectors.

![Attaching the motor cables](./_images/assembly/attaching_motor_cables.webp)

Insert the LiDAR cable into the bottom of the LiDAR.

![Inserting LiDAR cable into LiDAR](./_images/assembly/add_lidar_cable.webp)

Place the LiDAR on top of the circuit board, making sure the cable passes through the hole.

<img alt='LiDAR on top of circuit board' src='./_images/assembly/lidar_on_body.webp' width="49%"/>
<img alt='Cable coming out the other side' src='./_images/assembly/lidar_cable_below.webp' width="50%"/>

Using the provided hex key, attach the LiDAR to the rover's body using the bottom two mounting points.
For now, leave the third screw unattached.

![Attaching the LiDAR using the machine screws](./_images/assembly/screw_in_lidar_back.webp)

On the back, insert the LiDAR cable into its connector.

![Attaching the LiDAR cable](./_images/assembly/attach_lidar_cable.webp)

On the front of the rover, there are cutouts for attaching the skid.
Line the skid up with the cutouts, and push it on.
Use the final screw to attach the front skid. 

<img alt='Front skid before attachment' src='./_images/assembly/front_skid_before.webp' width="48%"/>
<img alt='Front skid after attachment' src='./_images/assembly/front_skid_after.webp' width="49%"/>

Insert the battery into the back of the rover.
Take note of polarity - the positive side of the battery (the end with a bump) goes towards the left.

<img alt='Empty battery holder' src='./_images/assembly/battery_empty.webp' width="50.5%"/>
<img alt='Battery holder with battery' src='./_images/assembly/battery_inserted.webp' width="48%"/>

Congrats! Your robot is assembled!

![Completed robot](./_images/assembly/complete_robot.webp)

## Care for Your Rover

The rover has a USB C port which you can use to charge the battery.
Two red status LEDs, directly below charging port, show the charging status.

The first LED, labeled CHARGING, lights up when the battery is actively being charged.
Once the battery is fully charged, this light will turn off.

The second LED, labeled PWR GOOD, lights up when a valid power supply is attached.

> [!WARNING]
> **Never charge Little Red Rover unattended.**
>
> If something goes wrong during the charging process, lithium batteries, like the one contained in the rover, are a serious fire hazard. If the battery becomes hot, smokes, swells, or gives off an odor during charging, immediately stop charging and dispose of the battery safely.

## Next Steps

Now that you have an assembled robot, head over to the [software setup](/software_installation) page to get the robot moving around!
