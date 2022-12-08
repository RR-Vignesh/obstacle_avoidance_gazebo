# obstacle-avoider
This is ENPM808X assignment

## Dependencies
* ros2 galactic
* dolly robot (git clone https://github.com/chapulina/dolly.git)
* geometry_msgs
* sensor_msgs

## Build/run steps

### Create a workspace 

```
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
```
### Clone the repo into src folder
```
git clone branch Week12_HW https://github.com/RR-Vignesh/obstacle_avoidance_gazebo.git
```

### Building dolly packages
```
colcon build
```

### Build the package
```
colcon build --packages-select obstacle-avoider
```
Source the terminal

```
source /opt/ros/galactic/setup.bash
. install/setup.bash
```
### 
```
ros2 launch my_package robot.launch.py
```

## Simulation Output Video
The simulation output video is available in the below link:
https://drive.google.com/file/d/1KYPS9RKzzgBERJ5pW6nN36-985M1n8JI/view?usp=sharing


### To run the ROS bag and capture data

```
ros2 launch obstacle_avoidance bag_record_launch.py bag_record:=True
ros2 bag record /ObstacleAvoidance
ros2 run obstacle_avoidance talker
```

### To view the recorded file info

```
ros2 bag info <foldername>
```

### To play the recorded file 
```
ros2 bag play <generated_folder>
```