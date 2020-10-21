***
# ORB_SLAM_2_ROS
+ ORB_SLAM_2_ROS setup for following nvidia boards
    + jetson TX2 - Jetpack 4.2
    + jetson Xavier NX - Jetpack 4.4
    + jetson Xavier
    <br>
+ version info
    + Ubuntu: 18.04 
    + ROS: Melodic 
    <br>
+ github link: [appliedAI-Initiative](https://github.com/appliedAI-Initiative/orb_slam_2_ros)
***
<br>

# Index
### 1. Prerequisites
####    &nbsp;&nbsp;&nbsp;&nbsp;● Eigen3
### 2. Installation
####    &nbsp;&nbsp;&nbsp;&nbsp;● Actually, there is no installation difference among TX2, Xavier, and NX
### 3. Jetson Boards
### 4. Run
<br><br>

## 1. Prerequisites
### ● Eigen3
```
$ sudo apt install -y libeigen3-dev
```
<br><br>

## 2. Installation
+ git clone and build from source with dependencies
```
$ cd ~/catkin_ws/src
$ git clone https://github.com/appliedAI-Initiative/orb_slam_2_ros
$ cd .. && rosdep install --from-paths src --ignore-src -r -y
$ catkin build -DCMAKE_BUILDTYPE=Release -j3
$ source ~/catkin_ws/devel/setup.bash
```
<br><br>

## 3. Jetson Boards
#### ● Actually, no installation difference among TX2, Xavier, and NX
<br><br>


## 4. Run
#### ● I used the stereo version. You can find the config file at config/RealSenseD435iStereo.yaml
#### ● you have to get a calibration data using [kalibr](https://github.com/zinuok/kalibr)
```
$ roslaunch realsense2_camera rs_camera.launch
$ roslaunch orb_slam2_ros orb_slam2_d435i_stereo.launch # made one for my d435i setup
$ rosrun rviz rviz -d [rviz config file path]
```

