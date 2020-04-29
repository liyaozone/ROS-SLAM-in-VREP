# ELCE5670_Final_Project
This is the final project for ELCE5670
## install ROS and V-REP
ROS version: [Kinetic](http://wiki.ros.org/kinetic/Installation/Ubuntu)
V-REP version: [V-REP_PRO_V3_6_2_Ubuntu16_04](https://www.coppeliarobotics.com/files/V-REP_PRO_V3_6_2_Ubuntu16_04.tar.xz)
steps:
+ `cd ~`
`https://www.coppeliarobotics.com/files/V-REP_PRO_V3_6_2_Ubuntu16_04.tar.xz`
`tar xf V-REP_PRO_V3_6_2_Ubuntu16_04.tar.xz`
`mv V-REP_PRO_V3_6_2_Ubuntu16_04 V-REP`
`roscore`
+ open another terminal
`cd ~/V-REP`
`./vrep.sh`
+ open scene "env.ttt" and press START button, open another ternimal
`rostopic list`
you can see the rostopics below:
/rosout
/rosout_agg
/tf
/vrep/camera_switch
/vrep/cmd_vel
/vrep/image
/vrep/laser_switch
/vrep/scan
