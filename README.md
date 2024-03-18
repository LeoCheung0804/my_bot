## How to install ROS2

[rolling](https://docs.ros.org/en/rolling/Installation.html),
[humble](https://docs.ros.org/en/humble/Installation.html),
[galactic](https://docs.ros.org/en/galactic/Installation.html),
[foxy](https://docs.ros.org/en/foxy/Installation.html)

## How to configuring your ROS 2 environment

[Configuring your ROS 2 environment](https://docs.ros.org/en/foxy/Tutorials/Configuring-ROS2-Environment.html)

## How to Create a ROS2 workspace

[ROS2 Tutorials Creating a workspace](https://docs.ros.org/en/foxy/Tutorials/Workspace/Creating-A-Workspace.html)


1. example, choose the directory name ros2_ws, for "development workspace" :

   ```bash
   mkdir -p ~/ros2_ws/src
   cd ~/ros2_ws/src
   ```
## Compile & Install ros2 package

1. Clone ros2 package from github

   Ensure you're still in the ros2_ws/src directory before you clone:

   ```bash
   git clone https://github.com/Slamtec/sllidar_ros2.git
   git clone https://github.com/orbbec/OrbbecSDK_ROS2.git
   git clone https://github.com/leocheung84/my_bot.git

   ``` 

2. Build packages

   Install deb dependencies

   ```bash
   # assume you have sourced ROS environment, same blow
   sudo apt install libgflags-dev nlohmann-json3-dev libgoogle-glog-dev \
   ros-humble-xacro ros-humble-joint-state-publisher-gui \
   ros-humble-rplidar-ros \
   ros-humble-image-transport ros-humble-image-publisher ros-humble-camera-info-manager
   ```

   From the root of your workspace (ros2_ws), you can now build package using the command:

   ```bash
   cd ~/ros2_ws/
   source /opt/ros/humble/setup.bash
   colcon build --symlink-install
   ```

3. Package environment setup

    ```bash
    source ./install/setup.bash
    ```

### Run node and view in the rviz

```bash
. ./install/setup.bash 
ros2 launch my_bot rplidar.launch.py 
```

```bash
. ./install/setup.bash 
ros2 launch orbbec_camera gemini2.launch.py
```

```bash
. ./install/setup.bash 
ros2 launch my_bot rsp.launch.py
```

#run joint sim
```bash
. ./install/setup.bash 
ros2 run joint_state_publisher_gui joint_state_publisher_gui
```