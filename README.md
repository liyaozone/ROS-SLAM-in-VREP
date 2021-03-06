# ROS SLAM in V-REP
DO SLAM based on ROS in V-REP environment
https://youtu.be/l-TuIQq4o6I
## install ROS and V-REP
ROS version: [Kinetic](http://wiki.ros.org/kinetic/Installation/Ubuntu)  
V-REP version: [V-REP_PRO_V3_6_2_Ubuntu16_04](https://www.coppeliarobotics.com/files/V-REP_PRO_V3_6_2_Ubuntu16_04.tar.xz)  
install V-REP
```
cd ~  
https://www.coppeliarobotics.com/files/V-REP_PRO_V3_6_2_Ubuntu16_04.tar.xz  
tar xf V-REP_PRO_V3_6_2_Ubuntu16_04.tar.xz  
mv V-REP_PRO_V3_6_2_Ubuntu16_04 V-REP  
roscore
```  
open another terminal  
```
cd ~/V-REP  
./vrep.sh  
```
open scene "env.ttt" and press START button, open another ternimal  
```
rostopic list  
```  
you can see the rostopics below:  
/rosout  
/rosout_agg  
/tf  
/vrep/camera_switch  
/vrep/cmd_vel  
/vrep/image  
/vrep/laser_switch  
/vrep/scan
## task2: control the robot with keyboard
we build a ros package named "key_teleop"  
```
rosmake key_teleop  
```
open another terminal  
```
rosrun key_teleop key_teleop.py  
```
"Key_teleop" is a node that will public message "geometry_msgs/Twist" to topic "/vrep/cmd_vel"  

## task1: Build 2D grid map with laserscan data and show it via rviz
We use hector slam to build the 2D grid map  
```
sudo apt-get install ros-kinetic-hector-slam  
```
open another terminal  
```
roslaunch hector_slam_mapping.launch  
```
By moving the robot with  keyboard, hector_slam will build the grid map.  
## task3: Image Recognition and localization.  
```
rosmake opencv_detector
```
move to the "opencv_detector/launch" folder  
```
roslaunch facedetector.launch  
```
move to the "src" folder  
```
rosmake image_marker  
rosrun image_marker image_marker  
```
## task 4: Visual Servoing
```
rosmake visual_servo  
rosrun visual_servo follow_ball  
```
## task 5: let the robot judge which area it locates  
```
rosmake loaction_judge  
rosrun location_judge location_judge  
```
## task6: Write a launch file to roslaunch all of above programs at once
```
roslaunch launch_all.launch  
```
You can launch all nodes at once
