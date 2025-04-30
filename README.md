# Pyrobosim-with-custom-world

Table of Contents:

  - [Overview](#overview)
  - [Demo](#demo)
  - [Features](#features)
  - [Project Structure](#projectstructure)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Acknowledgments](#acknowledgments)

## Overview

PyRoboSim is a lightweight 2D mobile robot simulator for behaviour prototyping. In this project, I used PyRoboSim to create a custom world of my institute building using its floor plan. It includes defining the office rooms and labs, hallways, some locations and objects from pick-and-place tasks and robots (IDOGs). For the robots, we also have the option to use different path planeers or write one. Here, I use A* and RRT planners. Various tasks like navigationg to rooms/locations, pick or place operations and detecting objects are available. To control the robots, we can use the GUI, python scripts or ROS actions/services.

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
pyrobosim-with-custom-world/
├── dependencies/                     # Project dependencies
├── docker/               # Docker image with the image
├── docs/                # Package documentation
├── pyrobosim/           # main folder for pyrobosim files
│   ├── 📂 examples/                  # Example scripts and demos
│   ├── 📂 pyrobosim/                 # Main Python package for Pyrobosim
│   ├── 📂 test/                      # Test scripts and configurations
│   ├── 📜 setup.py                   # Setup script for installation
│   ├── 📜 README.md                  # Project overview and documentation
├── pyrobosim_msgs/                      # pyrobosim message description for ROS action, services and topics
├── pyrobosim_ros/                      # Launch files for simulation and real-world runs
│   ├── 📂 examples/                  # Example scripts and demos of pyrobosim with ROS
│   ├── 📂 launch/                  # Example scripts and demos of pyrobosim with ROS
│   ├── 📂 pyrobosim/                 # Main Python package for Pyrobosim of pyrobosim with ROS
│   ├── 📂 test/                      # Test scripts and configurations of pyrobosim with ROS
│   ├── 📜 setup.py                   # Setup script for installation of pyrobosim with ROS
│   ├── 📜 README.md                  # Project overview and documentation of pyrobosim with ROS
├── setup/                        # bash setup files
├── test/                      # test files
├── CONTRIBUTING.md                     # contributors
├── LICENSE.md                     # license
├── README.md                      # README
├── docker-compose.yaml    
├── pyrobosim.env                      
├── pytest.ini                      
```


## Installation

Prerequisites
Follow this link to install and set up pyrobosim: https://pyrobosim.readthedocs.io/en/latest/setup.html
  
Clone and Build the Package

```bash
# Clone the repository
git clone https://github.com/PAyush15/Pyrobosim-with-custom-world/tree/main

```

## Usage

First, copy the idac_world.py file to the already set up pyrobosim environment or directly use the package

To run the world environment for robot navigation, run the idac_world.py file at the location 'pyrobosim/pyrobosim/examples/' folder by navigation to that folder in the terminal and simply running the python script: 'python3 idac_world.py --multirobot'

'--multirobot' argument launches the world with two robots which can be controlled independently.

On a separate thread, we run the tasks that we need to execute with the robot (Ex. nai=vigation, pick and place, etc.)


## Acknowledgments

Thanks to Sebastian Castro, the owner and maintainer of the PyRoboSim simulator for creaing this useful open-source tool. All rights and license for PyRoboSim used in this project belongs to Sebastian Castro.


