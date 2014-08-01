Setup walkthrough for model 601 devices 
=======

**Driver Setup:**
* cd to folder you want to store the drivers in.
* Run: `wget --no-check-certificate https://googledrive.com/host/0B9eIk6eTYsatMGlnV0Z1a0Z5MW8` (this downloads a .tar of the neccessary drivers)
* Run: `mv 0B9eIk6eTYsatMGlnV0Z1a0Z5MW8 drivers.tar`
* Run: `tar -xvf drivers.tar`
* Run: `sudo cd OpenNI-2.1.0-x64/ && ./install.sh && cd ..`
* Run: `sudo cd Sensor-Bin-Linux-x64-v5.1.6.6/ && ./install.sh && cd ..`
* Run: `sudo cd NITE-Bin-Dev-Linux-x64-v1.5.2.23/ && ./install.sh && cd ..`

**ROS Integration Setup:**

* Run: `sudo apt-get install libopenni2-0 libopenni2-dev`
* Run: `yujin_init_workspace openni2`
* Run: `cd openni2/src`
* Run: `git clone https://github.com/ros-drivers/openni2_camera.git`
* Run: `git clone https://github.com/ros-drivers/openni2_launch.git`
* Run: `../yujin_init_build --underlays "path to turtlebot workspace"`
* Run: `cd .. && yujin_make`
* 

**Final Setup:**
* Run: `sudo apt-get install g++ python libusb-1.0-0-dev libudev-dev freeglut3-dev doxygen graphviz`
* Run: `git clone https://github.com/occipital/OpenNI2.git`
* Run: `cd OpenNI2`
* Run: `git checkout -b develop origin/develop`
* Run: `git pull`
* Run: `make`


You can now: `roslaunch openni2_launch openni2.launch`
Bring up RVIZ to see the camera feeds. 

