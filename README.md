# AI in Robotics (AUT 2024) - Simulation Project

## Overview
This repository contains simulation environments and exercises designed for the "AI in Robotics" course at AUT University in 2024. The focus is on integrating artificial intelligence techniques with robotics, using Webots simulation environment.

## Overview of Exercise Series

In these exercise series, students will learn:

- [x] How to work with Webots.
- [x] Inverse kinematics and position control of the UR5e manipulator.
- [x] Pick and place using a vacuum gripper.
- [x] Object detection with a camera.
- [x] Automatic pick-and-place of objects using the manipulator.
- [ ] Classical model-based control of UR5e.

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

You can find the kinematics parameters form [here.](https://github.com/mhtayebzadeh/ai-in-robotics-course-project-AUT2024/blob/main/documents/ur5e-rgb-fact-sheet-landscape-a4.pdf)

For more simplicity, the DH parameters of UR5e are: 

d     =  [0.1625  , 0      , 0        ,0.133   ,0.0997  , 0.101 ]

a     =  [0       ,-0.425  ,-0.39225  ,0       ,0       ,0      ]

alpha =  [pi/2    , 0      , 0        ,pi/2    ,-pi/2    ,0      ]



### Exercise 2: Pick and Place with Known Object Positions
In this exercise, students will use the UR5e robot equipped with a Robotiq EPick Gripper to perform a pick-and-place task. The positions of the objects are known and provided manually.

This Gripper is a Vacuum Gripper with a length of 13 cm attached to the UR5e end-effector.

In the rest of the exercises, use "worlds/UR5e_vacuumGripper_camera.wbt". python example code is available in "controllers/my_controller/ur5e_vacuumGripper_camera.py".


1. Attach the Robotiq EPick Gripper to the UR5e robot in the simulation environment.
2. Manually set the positions of the objects on the table.
3. Program the robot to pick up each object and place it in baskets.
4. Verify the robot's ability to pick and place all objects accurately.


### Exercise 3: Pick and Place with Object Detection
This exercise extends the pick-and-place task by incorporating computer vision to detect and locate objects.


1. Use a camera in the simulation environment to capture images of the objects on the table.
2. Label the captured images and create a dataset for training a neural network.
3. Train or fine-tune a pre-trained network to detect objects and estimate their positions.
4. Program the robot to use the detected positions to perform the pick-and-place task.
5. Validate the performance of the vision system and the robot's ability to complete the task.



Output example:

![Pick and Place Example](https://github.com/mhtayebzadeh/ai-in-robotics-course-project-AUT2024/blob/main/documents/images/single_arm_vacuumGripper2.gif)






## Python Controller for UR5e Robot

The provided Python controller "my_controller/ur5e_vacuumGripper_camera.py" simplifies the access to the UR5e robot and includes methods to interact with the robot's joints, gripper, and sensors which are explained below.

### Methods and Functions

- **get_rgb_frame() -> np.ndarray**
  - Captures an RGB frame from the camera and converts it to a NumPy array.

- **get_depth_frame() -> np.ndarray**
  - Captures a depth frame from the range finder and converts it to a NumPy array.

- **UR5e Class**
  - **__init__(self, name="my_robot")**
    - Initializes the UR5e robot and sets up the motor devices, vacuum gripper, and GPS.
  
  - **set_arm_torques(self, torques)**
    - Sets the torques for the arm joints.

  - **set_gripper_pos(self, state='on')**
    - Activates or deactivates the vacuum gripper. `state` can be 'on' or 'off'.
  
  - **set_arm_pos(self, pos)**
    - Sets the positions for the arm joints.

  - **get_arm_pos(self) -> list**
    - Returns the current positions of the arm joints.

  - **get_gripper_pos(self) -> list**
    - Returns the current positions of the gripper joints.

  - **get_EE_position(self) -> list**
    - Returns the current position of the end effector using GPS data.

<!--
## Contributors
- [Your Name](https://github.com/yourusername) - Course Instructor

## License
This project is licensed under the [MIT License](LICENSE).
-->
