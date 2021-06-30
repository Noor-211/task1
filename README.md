task 1 :
***
- Create a workspace by using catkin_make :
the code :
   $ source /opt/ros/melodic/setup.bash
   $ mkdir -p ~/catkin_ws/src
   $ cd ~/catkin_ws/
   $ catkin_make 
- Installing the package arduino_robot_arm : 
the code :
Add the “arduino_robot_arm” package to “src” folder
	$ cd ~/catkin_ws/src
	$ sudo apt install git
	$ git clone https://github.com/smart-methods/arduino_robot_arm 
Install all the dependencies 
	$ cd ~/catkin_ws
	$ rosdep install --from-paths src --ignore-src -r -y
	$ sudo apt-get install ros-melodic-moveit
	$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
	$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
	$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control Compile the package
  $ catkin_make
- Controlling the motors :
  $ roslaunch robot_arm_pkg check_motors.launch 
- install Arduino IDE in Ubuntu :
  1-Install the Linux version from https://www.arduino.cc/en/Main/Software
  2- install rosserial by this code :
   $ sudo apt-get install ros-kinetic-rosserial-arduino
   $ sudo apt-get install ros-kinetic-rosserial
  3- Install the ros_lib library on the Arduino :
   $ cd <sketchbook>/libraries
   $ rm -rf ros_lib
   $ rosrun rosserial_arduino make_libraries.py .
- Run Rviz
   $ roslaunch robot_arm_pkg check_motors.launch
- Controlling the motors in simulation :
  first : 
  $ cd catkin_ws
  $ sourse devel/setup.bash
  $ roslaunch robot_arm_pkg check_motors.launch
  other terminal :
  $ cd catkin_ws
  $ sourse devel/setup.bash
  $ roslaunch robot_arm_pkg check_motors_gazebo.launch
  change the permission :
  $ cd catkin/src/arduino_robot_arm/robot_arm_pkg/scripts
	$ sudo chmod +x joint_states_to_gazebo.py
  then : 
  $ cd catkin_ws
  $ sourse devel/setup.bash
  $ rosrun robot_arm_pkg joint_states_to_gazebo.py
- movelt in Rviz :
  $ roslaunch moveit_pkg demo.launch
 - open robot_arm whith the Gazebo :
  $ roslaunch moveit_pkg demo_gazebo.launch
  
  
  
  

   
   
   

  



