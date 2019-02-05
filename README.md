This is the project repo for the final project of the Udacity Self-Driving Car Nanodegree: Programming a Real Self-Driving Car. For more information about the project, see the project introduction [here](https://classroom.udacity.com/nanodegrees/nd013/parts/6047fe34-d93c-4f50-8336-b70ef10cb4b2/modules/e1a23b06-329a-4684-a717-ad476f0d8dff/lessons/462c933d-9f24-42d3-8bdc-a08a5fc866e4/concepts/5ab4b122-83e6-436d-850f-9f4d26627fd9).


### System Architecture
The following is a system architecture diagram showing the ROS nodes and topics used in the project. 

![alt text](imgs/ROSArch.png)


### Traffic Light Detection
For this exercise, i used the test example in the Detection walkthrough tutorial.

### Waypoint Updater

The purpose of waypoint updater is to update the target velocity property of each waypoint based on traffic light and obstacle detection data. The target veloicty at normal situdation is given from `waypoint_loader node`. If the red light is detected, we genetated stopping trajectory considering vehicle's deceleration limits.

### Waypoint Follower

The longitudinal target velocity was set in waypoint_updater node. This node determine the target `yawrate` to keep the lane by using pure-pursuit algorithm.

### DBW(Drive-By-Wire) Node
This node finally calculates throttle, brake and steering angle to follow longitudinal and lateral trajectory simultaneously. We used PID controller to calculate throttle and brake based on the difference between the current velocity and the target velocity. We also use PID controller based on cross-track error (cte) to calculate appropriate steering command.

#### Individual submission
Jude Dike - dikejude49@gmail.com