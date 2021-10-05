# kubot_apriltag_detect

因為這邊使用catkin build, 建議不要放在kubot_ros/ros_ws當中, 另外開一個workspace.

## Install 
### [camera_image_pipeline](http://wiki.ros.org/image_pipeline)

```sh
# cd ~/another_workspace/src/
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

## 仿真測試

在kubot_init_env.sh當中選擇對應的鏡頭.
For example : Aider 在後方會裝上logitech C615, 在kubot 3d sensor選擇5.

1st Terminal:  

   ```sh
   # 啟動帶有apriltag和artag的模擬世界
   roslaunch kubot_gazebo kubot_syy_field.launch
   ```

2nd Terminal:

   ```sh
   # 啟動辨識apriltag並偵測tag_0, 其中完成tag_0到camera_link的TF轉換.

   # source ~/another_workspace/devel/setup.bash
   roslaunch kubot_apriltag_detect apriltag_detect_simulation.launch 
   ```

3rd Terminal:

   ```sh
   # 啟動鍵盤遙控車子觀察tag_0到robot的TF變化
   kubot_keyboard
   ```

## 真實車子

啟動整體車空節點即為

1st Terminal:  

   ```sh
   # 這將啟動KUBOT系列機器人的下位機控制, 機器人模型的TF, 所選擇的lidar, 所選擇的3d sensor
   roslaunch kubot_bringup robot.launch
   ```

2nd Terminal:

   ```sh
   # 啟動對應的apriltag辨識, 依據真實節點名稱修改launch檔
   # 無範例
   ```