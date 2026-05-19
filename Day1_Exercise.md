# (강의1): ROS2 토픽 복습과 Gazebo 로봇 실행

## ROS DOMAIN ID 설정 혹은 확인

echo $ROS_DOMAIN_ID

없거나 하나의 네트워크 내에서 겹치는 경우

export ROS_DOMAIN_ID=7

echo "export ROS_DOMAIN_ID=7" >> ~/.bashrc
source ~/.bashrc

## turtlesim 테스트

ros2 run turtlesim turtlesim_node

ros2 run turtlesim turtle_teleop_key

ros2 node list

ros2 topic info /turtle1/cmd_vel

ros2 topic echo /turtle1/pose

## mini pub sub
### ros2 workspace 생성 

mkdir -p ros2study_ws/src

cd ros2study_ws/src

ros2 pkg create mini_pubsub --build-type ament_python --dependencies rclpy std_msgs

소스코드 다운받아서 mini_pubsub/src 폴더 안에 위치시킨다.

### 빌드

cd

cd ros2study_ws

colcon build --packages-select mini_pubsub

### publisher 실행

source install/setup.bash

ros2 run py_pubsub minimal_publisher

### subscriber 실행

source install/setup.bash

ros2 run py_pubsub minimal_subscriber 



## Gazebo 실행

ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py


