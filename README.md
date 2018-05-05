# B(erkeley) L(ocalization) A(nd) M(apping)!

![alt text](https://github.com/erik-nelson/blam/raw/master/blam_mosaic.png)

***BLAM!*** is an open-source software package for LiDAR-based real-time 3D localization and mapping. ***BLAM!*** is developed by Erik Nelson from the Berkeley AI Research Laboratory ([BAIR](http://bair.berkeley.edu)). See https://youtu.be/08GTGfNneCI for a video example.

## Build Instructions
This repository is a static copy of the **BLAM!** repositor written by Erik Nelson. To finish installing it, simply cd to blam, and run catkin_make. 

## Run Instructions
***BLAM!*** is written in C++ with some Python interface elements, wrapped by
Robot Operating System ([ROS](http://ros.org)). Input LiDAR data should be
provided to the `/velodyne_points` topic using message type `sensor_msgs::PointCloud2`.

To run in online mode (e.g. by replaying a bag file from another terminal or
using a real-time sensor stream), use

```bash
roslaunch blam_example test_online.launch
```

To run in offline mode, i.e. by loading a bagfile and processing its data as
fast as possible, set the bagfile name and scan topic in
`blam_example/launch/test_offline.launch`, and use

```bash
roslaunch blam_example test_offline.launch
```

An example .rviz configuration file is provided under
`blam_example/rviz/lidar_slam.rviz`.

## Dependencies

***BLAM!*** relies on system installations of the following packages:

* [ROS](http://wiki.ros.org/ROS/Installation)
* [GTSAM](https://collab.cc.gatech.edu/borg/gtsam)

GTSAM in particular should be installed from source using the latest version of the develop branch from https://bitbucket.org/gtborg/gtsam. GTSAM relies on Boost, an incorrect version of which will interfere with some of ROS' packages if ROS is not upgraded to at least Indigo. ROS Indigo, in turn, relies on Ubuntu 14.04.
