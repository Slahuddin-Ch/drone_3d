# 3d_drone
To use this project on your local computer, clone it with these commands

    cd /catkin_ws/src
    git clone https://github.com/Slahuddin-Ch/drone_3d.git

## Prerequisites
To run this project, you must have a system with ROS Melodic and Teleop Twist Keyboard installed. Follow the instructions below for installation

    sudo apt-get install ros-melodic-teleop-twist-keyboard
    sudo apt-get install ros-melodic-ros-controllers

## 2D and 3D Mapping

After cloning the repository into src, run 

    cd /catkin_ws/ 
    catkin_make
 
To initialize the drone in gazebo, run the following command 
 
    roslaunch drone_test start.launch

Run 2D gmaping and 3D octomap mapping 

    roslaunch drone_test gmap.launch
    roslaunch octomap_server octomap_mapping.launch

Launch Rviz to visualize data

    rosrun rviz rviz

To control the drone with keyboard, use this command
   
    rosrun drone_test teleop.py

After running these commands, a gazebo world will be launched with the quadrotor stationary on the ground along with the rviz visualisation of the map. Add a marker array in the rviz window and changed the field to occupancy_marker_array. Go to the terminal window with the keyboard and start running the drone using teleop instructions. Once the drone takes off and starts navigating the world, the rviz visualization is populated with the occupancy map. You can save the map with 

    rosrun octomap_server octomap_saver -f my_octomap.ot
   for saving in octree format and 

    rosrun octomap_server octomap_saver -f my_octomap.bt
   for saving in binary tree format. 

## Map your own world 
You can map any world using this project. Just replace the new_world in Slahuddin-Ch/drone_3d/drone_test/worlds and rename it new_world. 
## Future work

 1. Deep Reinforecement Learning to eliminate the need of teleop
 2. LIO-SAM Mapping 
 3. 3D Navigation 

