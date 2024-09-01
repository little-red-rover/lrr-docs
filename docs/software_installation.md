# Software Installation

This tutorial will take you through the first time software setup for your rover. It should take around one hour.

## Dependencies

Little Red Rover relies on several pieces of software that must be installed.

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

```bash
git clone https://github.com/little-red-rover/lrr-template-project
```

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
