
# ROS2 node for libcamera supported cameras

### Dependencies
For ubuntu distros of raspi you'll need toinstall v4l2, cv2_bridge and libcamera. From our experience it is better to compile and install the raspberryPi version of the libcamera which can be found here "https://github.com/raspberrypi/libcamera". I removed libcamera from the package.xml since with docker the libcamera apt founds does not work in our case, so installing from source is the best option.

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
ros2 run camera_ros camera_node --ros-args -p width:=1920 -p height:=1080 -p format:= "UYVY"
```