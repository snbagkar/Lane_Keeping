# Lane_Keeping
Hi, I am Siddhesh Bagkar, graduate student at CU ICAR. This repository will enable you to perform Lane keeping using Computer vision Liabraries in python.
This project was carried out along with my classmate Ankit Verma. 

# Introduction
This repository contains information to run a racecar using Simple Lane keeping Algorithm in a Yellow single lane track. Lane-Keeping algorithm dictates the vehicle to detect the lanes and maintain the vehicle inside this lane seen by the sensor data. For Control, PID algorithm is implimented. Simulator is made using ROS/Gazebo. The simulation has been tested on and works well in Ubuntu 16.04 with ROS Kinetic installed.

# Requirements and Dependencies
```sh
  - sudo apt-get install ros-kinetic-ros-control 
  - sudo apt-get install ros-kinetic-gazebo-ros-control 
  - sudo apt-get install ros-kinetic-ros-controllerse
  - sudo apt-get install ros-kinetic-ackermann-msgs 
  - sudo apt-get install ros-kinetic-joy
 ```
# Launching the Yellow Lane world
The vehicle will be launched at the center of the circuit
```sh
$ roslaunch race f1_tenth.launch
```
# Teleoperating the vehicle on to the track
```sh
$ python keyboard.py
```
# Running the lane following algorithm
```sh
$ python test.py
```
# Image processing Pipeline 
  - Read image
  - Convert BGR image to RGB
  - Convert RGB to grayscale
  - Apply Canny edge detection on grayscale
  - Create region of interest
  - Apply Hough Line Transform
  - Create line over lanes 
  - Combine image
  
  
![Image Processing](https://github.com/snbagkar/Lane_Keeping/blob/main/6230e17a-59c4-400f-a3a7-0cdacc3448bd.jpeg)  

  
# For Controller basic PID controller is used 

        angle = previousAngle + kp*error + kd*(previousError - newError)
    
        velocity = previousVelocity + kp*error + kd*(previousError - newError)


# Final output
![Alt Text](https://github.com/snbagkar/Lane_Keeping/blob/main/AdvanceLaneKeeping-_2.gif)
