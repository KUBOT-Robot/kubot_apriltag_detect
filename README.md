# kubot_apriltag_detect

### [camera_image_pipeline](http://wiki.ros.org/image_pipeline)

```sh
# cd ~/your_workspace/src/
https://github.com/ros-perception/image_pipeline.git -b melodic
# 使用方範看wiki
```

### [apriltag_ros](http://wiki.ros.org/apriltag_ros)

```sh
# cd ~/your_workspace/src/
git clone https://github.com/AprilRobotics/apriltag.git
git clone https://github.com/AprilRobotics/apriltag_ros.git
# cd .. 
rosdep install --from-paths src --ignore-src -r -y 
```

```sh
catkin build
source ~/.bashrc
```


