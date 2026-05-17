#Setting Gazebo Turtlebot3

1. Install Gazebo
```python
sudo apt install ros-humble-gazebo-*
```

2. Install Cartographer
```python
sudo apt install ros-humble-cartographer
sudo apt install ros-humble-cartographer-ros
```

3. Install Navigation2
```python
sudo apt install ros-humble-navigation2
sudo apt install ros-humble-nav2-bringup
```

4. Install TurtleBot3 Packages
```python
source /opt/ros/humble/setup.bash
mkdir -p ~/turtlebot3_ws/src
cd ~/turtlebot3_ws/src/
git clone -b humble https://github.com/ROBOTIS-GIT/DynamixelSDK.git
git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3.git
sudo apt install python3-colcon-common-extensions
cd ~/turtlebot3_ws
colcon build --symlink-install
echo 'source ~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc
source ~/.bashrc
```

5. Environment Configuration
```python
echo 'export ROS_DOMAIN_ID=30 ' >> ~/.bashrc
echo 'export TURTLEBOT3_MODEL=burger ' >> ~/.bashrc
echo 'source /usr/share/gazebo/setup.sh' >> ~/.bashrc
echo 'source /opt/ros/humble/setup.bash' >> ~/.bashrc
source ~/.bashrc
```


