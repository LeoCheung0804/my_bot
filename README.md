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
   git clone https://github.com/leocheung0804/my_bot.git

   ``` 

2. Build packages

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