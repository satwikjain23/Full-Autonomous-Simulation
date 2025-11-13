
# Full Autonomous Simulation

This repository contains the race package implementing a complete autonomous driving pipeline in the F1TENTH simulator.
The system integrates perception, SLAM, path planning, and feedback control to enable a vehicle to navigate autonomously using cone-based track boundaries.

Developed and tested on ROS Noetic (Ubuntu 20.04).

![Autonomous Simulation Demo](./Untitled%20design.gif)


## Installation

Clone this repository into your ROS workspace and build it:

```bash
cd ~/catkin_ws/src
git clone https://github.com/satwikjain23/Full-Autonomous-Simulation.git
cd ~/catkin_ws
catkin_make
source devel/setup.bash

```
## Run

* Launch the simulator
```
rosrun f1tenth_simulator simulator.launch
```
<br>

* Run the Perception Node

```
rosrun race perception.py
```
> Detects and classifies cones using 2D LiDAR point cloud data to define track boundaries.
<br>

* Run the Control Node

```
rosrun race cones_control.py
```
> Applies a PID-based feedback controller to minimize steering angle errors.
<br>

* Run the Path Planning Node

```
rosrun race cones_distfinder.py
```
> Generates a smooth centerline trajectory between detected cones using the mid-point algorithm.
<br>

* Run the SLAM Node

```
rosrun race slam.py
```
> Estimates the vehicle’s position and orientation by using IMU, and GPS data

    
