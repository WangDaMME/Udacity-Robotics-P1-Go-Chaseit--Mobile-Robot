# Udacity-Robotics-P1-Go-Chaseit--Mobile-Robot


## Overview
In this fun project, I create a ball-chaser robot and control its motion by communicating with 2 ROS packages. 
Firstly inside my_robot package, the 4-wheel robot is defined with the URDF format and is added with features and Gazebo Plugins including camera, lidar, the "skid_steer_drive_controller". 
Secondly inside ball_chaser package, the process_image node analyzes the image captured by the camera to determine the position of a white ball. Then the robot calls the drive_bot node to actuate itself toward the ball. The nodes in ball_chaser will communicate with the my_robot package by subscribing to the robot camera sensor and publishing to the robot’s wheel joints.

![sdd](https://user-images.githubusercontent.com/48291391/61405312-7b1cca80-a8a7-11e9-9793-5c43851a68b3.gif)

## Directory Structure
```
   .Project1                           # Go Chase It Mobile Robot
    ├── my_robot                       # my_robot package                   
    │   ├── launch                     # launch folder for launch files   
    │   │   ├── robot_description.launch
    │   │   ├── world.launch
    │   ├── meshes                     # meshes folder for sensors
    │   │   ├── hokuyo.dae
    │   ├── urdf                       # urdf folder for xarco files
    │   │   ├── my_robot.gazebo
    │   │   ├── my_robot.xacro
    │   ├── world                      # world folder for world files
    │   │   ├── world.world
    │   ├── CMakeLists.txt             # compiler instructions
    │   ├── package.xml                # package info
    ├── ball_chaser                    # ball_chaser package                   
    │   ├── launch                     # launch folder for launch files   
    │   │   ├── ball_chaser.launch
    │   ├── src                        # source folder for C++ scripts
    │   │   ├── drive_bot.cpp
    │   │   ├── process_images.cpp
    │   ├── srv                        # service folder for ROS services
    │   │   ├── DriveToTarget.srv
    │   ├── CMakeLists.txt             # compiler instructions
    │   ├── package.xml                # package info                  
    └──                              
```

## Launch The Project

  1. Clone/Download this project.
  2. Build the project
```
  $ cd /home/workspace/catkin_ws
  $ catkin_make
```
  3. Launch the robot inside the world
```
  $ cd /home/workspace/catkin_ws/
  $ source devel/setup.bash
  $ roslaunch my_robot world.launch
```
  4. Launch ball_chaser to run drive_bot Node & process_image Node
```
  $ cd /home/workspace/catkin_ws/
  $ source devel/setup.bash
  $ roslaunch ball_chaser ball_chaser.launch
```
  5. Visualize the robot's camera images
```
  $ rosrun rqt_image_view rqt_image_view  
```
