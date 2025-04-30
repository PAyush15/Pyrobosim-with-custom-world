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
pyrobosim-with-custom-world/
├── dependencies/                     # Project dependencies
├── docker/               # Docker image with the image
├── docs/                # Package documentation
├── pyrobosim/           # main folder for pyrobosim files
├── pyrobosim_msgs/                      # pyrobosim message description for ROS action, services and topics
├── pyrobosim_ros/                      # Launch files for simulation and real-world runs
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


## License

This project is licensed under the MIT License.
Feel free to use, modify, and distribute — just give credit where it’s due!

## Acknowledgments

Thanks to BVM Alumni Association for project funding

Special thanks to Prof. Dr. Vinay Patel for mentorship and guidance


