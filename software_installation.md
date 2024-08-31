# Software Installation


## Dependencies

Little Red Rover uses Docker as a compatability layer with your host operating system.
The steps for installing Docker differ depending on your host OS.

TODO: Docker installation for Mac, windows, linux, ect

For a new user, Docker can have a steep learning curve. Luckily, the [DevContainers]() project allows for seamless integration within your editor.
VSCode has first class support for DevContainers, and is the recommended editor for LRR.

TODO: VsCode installation for Mac, windows, linux, ect

Once VSCode is installed, use the extension manager to install the DevContainers extension.

TODO: How to install extension

Lastly, LRR uses Git / Github for source code management. To download the source code, you must first install git. 

TODO: How to install Git

## Setting Up Your Development Environment

Our first step is to download the LRR source. 

TODO

Next, we need to open the project in VSCode.

TODO

Finally, open the project using the DevContainers extension. This first installation will take some time (you're downloading all of Ubunutu and ROS2 after all).
It's recommended to use a strong internet connection during this initial setup.

TODO

Congrats! Your development enviroment is now setup.

## Connecting to the Robot


## Rock and Roll

Now that the robot is setup, lets have some fun. To start a demo, run the following commands in your VSCode shell:

To build the ROS2 project:

```bash
lrr_build
```

To run the demo:

```bash
lrr_run
```

## Troubleshooting
