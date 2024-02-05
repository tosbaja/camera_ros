# ROS2 node for libcamera supported cameras

### Dependencies

For ubuntu distros of raspi you'll need toinstall v4l2, cv2_bridge and libcamera. From our experience with **raspberry pi 5** compiling libcamera from the raspberryPi [respository](https://github.com/raspberrypi/libcamera) is the only way to work with **raspberry pi 5** and **Raspicam v1.3 ov5647** in docker enviroment (Jammy 22.04.3). The package camera_ros can be installed with apt, but since it depends to libcamera and the version available on apt wont work with **raspberry pi 5** I removed libcamera from the package.xml and created a new fork of the repo, so compiling camera_ros from [here](https://github.com/tosbaja/camera_ros.git) and with the raspberryPi [libcamera](https://github.com/raspberrypi/libcamera) version is the only option.

### To run

```
ros2 run camera_ros camera_node
```

### Parameters
#### Format
Video format for streaming. You may need to change this parameter for your camera.

#### Role
Camera role, options: raw, still, video, viewfinder.

#### Width
Width for the stream

#### Height
Height for the stream

#### Camera
ID of the camera

#### Example run command with params

```
ros2 run camera_ros camera_node --ros-args -p width:=1920 -p height:=1080 -p format:="UYVY"
```