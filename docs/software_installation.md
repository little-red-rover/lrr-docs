# Software Installation

This tutorial will take you through the first time software setup for your rover. It will require 15 minutes of active time and 45 minutes for downloading / building.

## Dependencies

Little Red Rover relies on several pieces of software that must be installed prior to working with the robot.

### Docker

Little Red Rover uses Docker as a compatability layer with your host operating system.

<!-- tabs:start -->

#### **Windows**

Follow the [installation instructions](https://docs.docker.com/desktop/install/windows-install/) from the Docker website.

#### **MacOS**

Follow the [installation instructions](https://docs.docker.com/desktop/install/mac-install/) from the Docker website.

#### **Linux**

Follow the [installation instructions](https://docs.docker.com/desktop/install/linux-install/) from the Docker website.
<!-- tabs:end -->

### VSCode

To make working with Docker painless, its recommended to use the devcontainers feature of the VSCode. First, download VSCode if you don't have it installed already.

<!-- tabs:start -->

#### **Windows**

Follow the [installation instructions](https://code.visualstudio.com/download) from the VSCode website.

#### **MacOS**

Follow the [installation instructions](https://code.visualstudio.com/download) from the VSCode website.

#### **Linux**

Follow the [installation instructions](https://code.visualstudio.com/download) from the VSCode website.

<!-- tabs:end -->

Next, install the devcontainers extension [using the instructions here](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).

### Git

Lastly, the project uses Git for source code management. 

<!-- tabs:start -->

#### **Windows**

Follow the [installation instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) from the Git website.

#### **MacOS**

Follow the [installation instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) from the Git website.

#### **Linux**

Follow the [installation instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) from the Git website.

<!-- tabs:end -->


## Setting Up Your Development Environment

Open VSCode, then open a folder where you'd like to store the project (File -> Open Folder).
Start a new terminal (Terminal -> New Terminal) and run the following command to pull a template project:

<!-- tabs:start -->

#### **ROS2: Humble (Recommended)**

```bash
git clone https://github.com/little-red-rover/lrr-template-project
```

#### **ROS1: Noetic**

```bash
git clone https://github.com/little-red-rover/lrr-template-project && checkout noetic
```


<!-- tabs:end -->

> [!INFO]
> ROS1 is nearing end of life. For new projects, it is highly recommended to use the most recent long term support (LTS) ROS2 distribution.

Next, open the project:

```bash
cd lrr-template-project && code .
```

Finally, start the devcontainer (View -> Command Palate -> (type) "Rebuild and Reopen in Container").

> [!INFO]
> Mac and Windows users, Docker Desktop must be started before opening the container.

The first time building the container will take some time (30+ minutes). This only has to happen once, in the future it will be much quicker.


You should now have an open VSCode window running the developement container. 

## Connecting to the Robot

Power on your rover using the switch on the left side (near the usb port).
You'll know its turned on when the LiDAR on top starts spinning.
On boot up, the robot creates a wifi hotspot. Connect your development computer to the network named "little_red_rover".

Open a terminal in your VSCode window (Terminal -> New Terminal) and enter the following command.

```bash
lrr_connect
```

Follow the instructions in the terminal to connect the robot to a wifi network.

## Run Teleop

In your terminal, run

```bash
lrr_build
```

then

```bash
lrr_run
```

## Setup Foxglove

Foxglove is a tool we use for visualizing and controlling the rover.
[Create an account on Foxglove](https://app.foxglove.dev/), then select "Open Connection". In the following popup, leave 'Foxglove Websocket' selected the default value of 'ws://localhost:8765' for the url. Click 'Open'.

In the top right corner, find the button that says 'Layout'. In the drop down, select 'Import From File...' then navigate to '(template project installation path)/tools/lrr_default_layout.json'.

## Troubleshooting

Check out the [troubleshooting page](/troubleshooting).

