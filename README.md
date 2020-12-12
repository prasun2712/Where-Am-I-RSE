# Where-Am-I-RSE

## Project Overview
Welcome to the Where Am I? localization project! In this project, you will learn to utilize ROS AMCL package to accurately localize a mobile robot inside a map in the Gazebo simulation environments.

* Create a ROS package that launches a custom robot model in a custom Gazebo world

* Utilize the ROS AMCL package and the Tele-Operation / Navigation Stack to localize the robot

* Explore, add, and tune specific parameters corresponding to each package to achieve the best possible localization results

## Folder Content
* **Where-Am-I-RSE**
    * **catkin_ws**
        * **src**
            * **ira_laser_tools** - Package to merge two laser scan data. (My robot has two 2-D lidar)
            * **pgm_map_creator** - Create map from gazebo world.
            * **my_robot** :
                * **config** - Contains config files for navigation and also rviz file.
                * **launch** - Contains all the launch files :
                    * **all_in_one.launch** - To include all the launch files at once.
                    * **amcl.launch** - Launch file for amcl.
                    * **map_server.launch** - Launch file for map server.
                    * **merger_scan.launch** - Launch file to merge two laser scan data.
                    * **move_base.launch** - Launch file for move_base node and load params.
                    * **skid_steer_diff_bot_base_laser.launch** - Launch file to load robot xacro and run robot_state_publisher and joint_state_publisher.
                    * **teleop.launch** - Launch file for teleop node.
                    * **world.launch** - Launch file to spawn robot in world
                * **maps** - Contains map file and map metadata.
                * **meshes** - Contains mesh files.
                * **urdf** - Contains robot related xacros.
                * **world** - Contains my world file.
            * **teleop_twist_keyboard** - Tele-operation package.
    * **images** - Assignment images.

## Images for assignment
* Gazebo World with the **Robot** localised in it, **AMCL particles** are shown in **Red**.
![](https://github.com/prasun2712/Where-Am-I-RSE/blob/main/images/world_and_robot_view.png "Gazebo World with the Robot localised in it, AMCL particles are shown in Red")

* Close-up view of the **Robot**.
![](https://github.com/prasun2712/Where-Am-I-RSE/blob/main/images/robot_closeup.png "Close-up view of the Robot")

## Prerequisite
* Basic knowledge of ROS.
* ROS Kinetic installed.
* ros-kinetic-navigation, ros-kinetic-map-server, ros-kinetic-move-base, ros-kinetic-amcl, ros-kinetic-dwa-local-planner
                            
## Build and Run
```
cd ~/
git clone https://github.com/prasun2712/Where-Am-I-RSE.git
cd ~/Where-Am-I-RSE/catkin_ws
catkin_make
```
***Terminal 1***
```
roslaunch my_robot all_in_one.launch
```
***Terminal 2***
```
roslaunch my_robot teleop.launch
```