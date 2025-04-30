# Pyrobosim-with-custom-world

Table of Contents:

  - [Overview](#overview)
  - [Demo](#demo)
  - [Features](#features)
  - [Project Structure](#projectstructure)
  - [Installation](#installation)
  - [Usage](#usage)
  - [License](#license)
  - [Acknowledgments](#acknowledgments)

## Overview

PyRoboSim is a lightweight 2D mobile robot simulator for behaviour prototyping. In this project, I use PyRoboSim to creation a custom world (and additionaly a gazebo environment) of my institute using the floor plan. 

Consider the above image. The world is created solely using pyrobosim. pyrobosim is primarily a world modeling framework for prototyping high-level robotics behavior applications.


## Demo

![Screenshot from 2025-02-05 11-33-10](https://github.com/user-attachments/assets/5ec81690-0c4c-4fcf-8ae8-8b95faee0177)

## Features

- **Build complex worlds** using the world modeling framework, both manually and programmatically.

- **Define custom actions and action executors** (e.g., path planning/following or decision-making algorithms).

- **Design task and motion planners** that go from task specification to an executable plan.

- **Export worlds to Gazebo** to test in a 3D world with more complex sensing and actuation models.


## Project Structure

### 📁 Project Structure

```plaintext
autonomous-indoor-delivery-robot-main/
├── 📜 README.md                     # Project overview and documentation
├── 📜 qrcode_scan.py               # QR code detection script (Jetson Nano + Pi Cam)
├── 📜 rosserial.ino                # Arduino code for servo/buzzer control

├── 📂 adbot_description/           # URDF and package description for adbot
│   ├── 📂 config/                      # ROS configuration and parameter files
│   ├── 📂 launch/                      # Launch files for simulation and real-world runs
│   ├── 📂 maps/                        # Saved maps for navigation
│   ├── 📂 meshes/                      # STL files for 3D components
│   ├── 📂 params/                      # Navigation parameter files (e.g., global_costmap_params.yaml)
│   ├── 📂 scripts/                     # ROS Python nodes for robot behavior
│   ├── 📂 urdf/                        # URDF files of the robot
│   ├── 📂 worlds/                      # Custom Gazebo world files
│   ├── 📜 CMakeLists.txt               # Build instructions for catkin
│   ├── 📜 package.xml                  # ROS package metadata

├── 📂 rmp_bot_description/         # URDF and package description for rmp_bot
│   ├── 📜 CMakeLists.txt
│   ├── 📜 LICENSE
│   ├── 📜 package.xml

├── 📂 ros_controllers-melodic-devel/  # External ROS control package fork
│   ├── 📜 .gitignore
│   ├── 📜 .travis.yml
│   ├── 📜 README.md
```



## Installation

Prerequisites
Ensure you have ROS Noetic installed on Ubuntu 20.04. If not, install it:
```bash
sudo apt update
sudo apt install ros-noetic-desktop-full
  ```
Initialize rosdep and set up your environment:

```bash
sudo rosdep init
rosdep update
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
  ```

Install Required ROS Packages

```bash
sudo apt install -y \
  ros-noetic-navigation \
  ros-noetic-slam-gmapping \
  ros-noetic-teleop-twist-keyboard \
  ros-noetic-robot-state-publisher \
  ros-noetic-joint-state-publisher-gui \
  ros-noetic-xacro \
  ros-noetic-gazebo-ros \
  ros-noetic-map-server \
  ros-noetic-amcl \
  ros-noetic-rviz \
  python3-rosdep \
  python3-rosinstall \
  python3-vcstools \
  python3-catkin-tools
  ```
  
Clone and Build the Package

```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src

# Clone the repository
git clone https://github.com/PAyush15/autonomous-indoor-delivery-robot

# Build the workspace
cd ~/catkin_ws
catkin build

# Source the setup file
source devel/setup.bash
```

## Usage

To run the world environment for robot navigation, run the idac_world.py file at the location 'pyrobosim/pyrobosim/examples/' folder by navigation to that folder in the terminal and simply running the python script: 'python3 idac_world.py --multirobot'

'--multirobot' argument launches the world with two robots which can be controlled independently.

On a separate thread, we run the tasks that we need to execute with the robot (Ex. nai=vigation, pick and place, etc.)


## License

This project is licensed under the MIT License.
Feel free to use, modify, and distribute — just give credit where it’s due!

## Acknowledgments

Thanks to BVM Alumni Association for project funding

Special thanks to Prof. Dr. Vinay Patel for mentorship and guidance


