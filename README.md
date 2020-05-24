# IMU tools for ROS

* http://wiki.ros.org/imu_tools

-----

## Overview

IMU-related filters and visualizers. The stack contains:

 * `imu_filter_madgwick`: a filter which fuses angular velocities, accelerations, and (optionally) magnetic readings from a generic IMU device into an orientation. Based on the work of [1].

 * `imu_complementary_filter`: a filter which fuses angular velocities, accelerations, and (optionally) magnetic readings from a generic IMU device into an orientation quaternion using a novel approach based on a complementary fusion. Based on the work of [2].

 * `rviz_imu_plugin` a plugin for rviz which displays `sensor_msgs::Imu`
messages

References:
* [1] http://www.x-io.co.uk/open-source-imu-and-ahrs-algorithms/
* [2] http://www.mdpi.com/1424-8220/15/8/19302


## Build

```sh
# Create a catkin workspace
mkdir -p ws_ins/src
cd ws_ins/src

# Download the stack
git clone -b <distro> https://github.com/cggos/imu_tools.git

# Install any dependencies (optional)
rosdep install imu_tools

cd ..

# Compile the stack
catkin_make 
# or
catkin build
```

## Run

* run imu_filter_madgwick

  ```sh
  rosrun imu_filter_madgwick imu_filter_node \
    _use_mag:=false _publish_debug_topics:=true /imu/data_raw:=/mynteye/imu/data_raw
  ```

  or

  ```sh
  roslaunch imu_filter_madgwick imu_filter_madgwick.launch camera:=mynteye
  ```
