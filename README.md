# _Nursing robot_

Nursing robot uses the Evarobot for ROS Noetic.

![Image of Evarobot](https://raw.githubusercontent.com/inomuh/evarobot/main/images/evarobot.png)

In this package there are:
- evarobot_description: It is the sub-package containing urdf and mesh files of the Evarobot.
- evarobot_simulation: It is a sub-package containing the package and launch files required for the simulation of the Evarobot.
- evarobot_slam: It is a sub-package containing the slam_gmapping launch files.
- evarobot_navigation: It is a sub-package containing the navigation launch and config files.
- nursing_robot: It is a sub-package containing the world file, a launch file required for Gazebo simulation 

Launch Command:
----------------
----------------
Hospital World in Gazebo:

        $ roslaunch nursing_robot evarobot_world.launch

SLAM Mapping Launching (must work with _Hospital World in Gazebo_ file):

        $ roslaunch evarobot_slam evarobot_slam.launch
    
Teleop_twist_keyboard: 

        $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py

Navigation Launching:

        $ roslaunch evarobot_navigation evarobot_navigation.launch

Node for setting initial pose and send navigation goal (must work with _Navigation Launching_ file):

        $ roslaunch evarobot_navigation initpose_nav_goal.py

![Image of Navigation](https://raw.githubusercontent.com/Jasmimma/Nursing_robot/main/Gazebo_nav.png)
![Image of Navigation](https://raw.githubusercontent.com/Jasmimma/Nursing_robot/main/Rviz_nav_node.png)

-----------------------------------------------------------------------------------------------------------------------

-------------
Requirements:
-------------
- In order for the "joint_state_publisher" to work, "joint_state_publisher_gui" package must be downloaded 

        $ sudo apt update && sudo apt install ros-noetic-joint-state-publisher-gui
        
- In order for the "joint_state_controller" to work, "joint_state_controller_gui" package must be downloaded.

        $ sudo apt-get install ros-noetic-ros-control
        $ sudo apt install ros-noetic-ros-controllers
        
- In order for the sensors to work properly, "gazebo_ros_pkgs" files must be downloaded.

        $ sudo apt-get install ros-noetic-gazebo-ros-pkgs
    
- In order for the "driver_base" to work, "driver_base" package must be downloaded.
 
        $ cd ~/catkin_ws/src && git clone https://github.com/ros-drivers/driver_common -b indigo-devel
        
- In order for the SLAM to work, "slam_gmapping" package must be downloaded.

        $ sudo apt-get install ros-noetic-slam-gmapping
        
- In order to drive the robot, "teleop-twist-keyboard" must be downloaded.

        $ sudo apt-get install ros-noetic-teleop-twist-keyboard
        
- In order for the navigation tools to work properly, "ros-navigation" and "teb-local-planner" must be downloaded.

        $ sudo apt-get install ros-noetic-ros-navigation
        $ sudo apt-get install ros-noetic-teb-local-planner
-------------------------------------------------------------------------------
