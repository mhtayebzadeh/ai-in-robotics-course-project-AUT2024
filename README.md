# AI in Robotics (AUT 2024) - Simulation Project

## Overview
This repository contains simulation environments and exercises designed for the "AI in Robotics" course at AUT University in 2024. The focus is on integrating artificial intelligence techniques with robotics, using Webots simulation environment.

## Overview of Exercise Series

In these exercise series, students will learn:

- [x] How to work with Webots.
- [ ] Inverse kinematics and position control of the UR5e manipulator.
- [ ] Classical model-based controllers.
- [ ] Object detection with a camera.
- [ ] Automatic pick-and-place of objects using the manipulator.

## Simulation Environment
The simulation environment features a UR5e manipulator equipped with a "ROBOTIQ 2F-140 Gripper". 
The UR5e is a versatile 6 DoFs robotic arm manufactured by Universal Robots. It is widely used in industrial automation and research applications due to its precision and flexibility. [Try it online.](https://webots.cloud/run?version=R2023b&url=https%3A%2F%2Fgithub.com%2Fcyberbotics%2Fwebots%2Fblob%2Freleased%2Fprojects%2Frobots%2Funiversal_robots%2Fprotos%2FUR5e.proto)

<!--
## Getting Started
To get started with the exercises, follow these steps:
1. Clone this repository to your local machine or download .zip file.
2. Set up the Webots simulation environment according to the provided instructions.
3. Navigate to the respective exercise folders and follow the instructions provided in the README files.
-->

## Exercises
### Exercise 1: Inverse Kinematics
Students will be introduced to solving inverse kinematics for the UR5e manipulator. They will learn to calculate joint angles required to achieve a desired end-effector position. (numerically or analytically)

Pick up the cylindrical object from the table at position P1 = [-0.6, 0.2, 0.8] and place it on another table at position P2 = [0.65, -0.3, 0.6]. UR5e robot origin placed at P_base = [0, 0, 0.6]. [Video](https://webots.cloud/AccUng0)

You can find the kinematics parameters form [here.](https://github.com/mhtayebzadeh/ai-in-robotics-course-project-AUT2024/documents/ur5e-rgb-fact-sheet-landscape-a4.pdf)

For more simplicity, the DH parameters of UR5e are: 

d     =  [0.1625  , 0      , 0        ,0.133   ,0.0997  , 0.101 ]

a     =  [0       ,-0.425  ,-0.39225  ,0       ,0       ,0      ]

alpha =  [pi/2    , 0      , 0        ,pi/2    ,pi/2    ,0      ]


<!-- 
### Exercise 2: Object Detection and Grasping

### Exercise 3: Object Manipulation
-->

<!--
## Contributors
- [Your Name](https://github.com/yourusername) - Course Instructor

## License
This project is licensed under the [MIT License](LICENSE).
-->
