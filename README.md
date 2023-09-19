nav2 simple commander api

😀️LAUNCH:
export TURTLEBOT3_MODEL=burger
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py

RUN SLAM:

ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True

CONTROL:
ros2 run turtlebot3_teleop teleop_keyboard

LAUNCH:


😀️STEPS:
SOurce command:
{new1}
source ros_ws/ros2_learners/navigation_tb3/install/setup.bash

ros_ws/ros2_learners/navigation_tb3
colcon build

{new2}

source ros_ws/ros2_learners/navigation_tb3/install/setup.bash

ros2 launch navigation_tb3 navigation.launch.py
 ros2 launch turtlebot3_gazebo turtlebot3_dqn_stage4.launch.py 


{new 3}
source ros_ws/ros2_learners/navigation_tb3/install/setup.bash

ros2 run navigation_tb3 single_goal_nav.py


😀️Listener Talker
(Talker)
cd ros2_ws/
rosdep install -i --from-path src --rosdistro humble -y
colcon build --packages-select py_pubsub
source install/setup.bash
ros2 run py_pubsub talker

(Listener)
cd ros2_ws/
colcon build --packages-select py_pubsub
source install/setup.bash
ros2 run py_pubsub listener

(Transform)
cd ros2_ws/
colcon build --packages-select py_pubsub
source install/setup.bash
ros2 run py_pubsub transform

(Random Coordinates)
cd ros2_ws/
colcon build --packages-select py_pubsub
source install/setup.bash
ros2 run py_pubsub random


😀️(RQT GUI)
ros2 run rqt_gui rqt_gui

(Give exact position to robot)
ros2 topic pub --once /position geometry_msgs/msg/Point "{x: 2.298, y: -1.388, z: 0}"

😀️ROS TEST
u = 0.08;
w = 0.00;
node = ros2node('MATLAB');
velocityPub = ros2publisher(node, "/rand_vel", "geometry_msgs/Twist");
msg = ros2message(velocityPub);
msg.linear.x = u;
msg.angular.z = w;
send(velocityPub, msg);


😀️Open MATLAB
cd /usr/local/MATLAB/R2023a/bin/
./matlab




😀️ using matlab to move robot
cd ros2_ws
source install/setup.bash
ros2 node info /MATLAB
ros2 topic echo /position
ros2 launch navigation_tb3 navigation.launch.py
{new}
cd ros2_ws
source install/setup.bash
ros2 run py_pubsub listener
 
😀️Aquila Ros, MATLAB
cd /usr/local/MATLAB/R2023a/bin/
./matlab
{new1}
 cd ros2_ws
 source install/setup.bash
 ros2 topic echo /position
 run on MATLAB on verrify
{new2}
cd ros2_ws
 source install/setup.bash
 ros2 run py_pubsub listener
 {new3}
 cd ros2_ws
 source install/setup.bash
ros2 launch navigation_tb3 navigation.launch.py
{new4}
cd ros2_ws
source install/setup.bash
ros2 run py_pubsub transform
run AQUILA Code from MATLAB
  
  
😀️ To Generate and save map
1. Launch Map, Cartographer, Teleop, and manually make the map in rviz
2. open directory where you want to save map
in mmy case; cd ros2_ws/ros2_learners/navigation_tb3/config
3. save map using, ros2 run nav2_map_server map_saver_cli -f maps/stage4_map
  
  
  
😀️ Run ws (multi-robot)
cd ws 
colcon build
source ~/ws/install/setup.bash
{new}
ros2 launch tb3_sim multi_tb3_simulation_launch.py


😀️ Sir Luqman
ros2 launch turtlebot3_gazebo turtlebot3_dqn_stage4.launch.py
ros2 launch navigation_tb3 mapping.launch.py
rviz2



😀️STAGE 4 Ros, MATLAB
cd /usr/local/MATLAB/R2023a/bin/
./matlab
{new1}
 cd ros2_ws
 source install/setup.bash
 ros2 topic echo /position
 run on MATLAB on verrify
{new2}
cd ros2_ws
 source install/setup.bash
 ros2 run py_pubsub listener
 {new3}
cd Downloads/stage4_ws/
cd Downloads/stage3_ws/
cd Downloads/stage1_ws/ (dynamic st 1,2)
cd Downloads/cae_ws/ (cae world)
cd Downloads/multipleobstacle_ws/ (multiple obstacle world)


source install/setup.bash
source /usr/share/gazebo/setup.bash
ros2 launch navigation_tb3 navigation.launch.py 
{new4}
cd ros2_ws
source install/setup.bash
ros2 run py_pubsub transform
run AQUILA Code from MATLAB
{NEW 5}
ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True
{NEW 6}
ros2 run rqt_gui rqt_gui

ros2 run turtlebot3_teleop teleop_keyboard



source /opt/ros/humble/setup.bash 
source /usr/share/gazebo/setup.bash
echo "export TURTLEBOT3_MODEL=burger >>~/.bashrc
https://github.com/noshluk2/ros2_learners



