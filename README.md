# The Dark Mole
The four wheeled robot needs initial aid from you. He can't begin his journey without installing some soft- and hardware.

##Requirements
1. The *Raspberry Pi 3 Model B* is the brain of your robot.
2. The *[RPLIDAR A1](http://www.slamtec.com/en/lidar/A1)* or *[RPLIDAR A2](http://www.slamtec.com/en/lidar)* are the eyes and make your robot feel comfortable in its environment.
3. Lot of your time. Be patient. Bring to your mind that most of the project stuff will only work on the second or third go and definitively not on the first run.

## Installing Ubuntu
Your robot needs an operating system to run the [Robot Operating System (ROS)](http://www.ros.org/):

1. Download the latest [Ubuntu image](https://ubuntu-pi-flavour-maker.org/download/). For us the Ubuntu Server Minimal edition worked.
2. Extract the image on your microSDHC. See the chapter [Making a microSDHC](https://ubuntu-pi-flavour-maker.org/download/).

## Connecting to your Raspberry Pi
You should know how to connect to your Raspberry Pi. If not demonstrate your intelligence and read yourself through the internet. In the end you need a working shell and a working internet connection from your Raspberry Pi.

The standard user and password for the Ubuntu image are *ubuntu* and *ubuntu*. See also the [FAQ](https://ubuntu-pi-flavour-maker.org/faq/).

If you want to set up a WiFi connection for your Raspberry you may want to take a look [here](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md). If you are unfamiliar with *wpa_supplicant* and its configuration [click here (German)](https://wiki.ubuntuusers.de/WLAN/wpa_supplicant/).

If you have an unfamiliar keyboard layout, enter the following command to adapt your keyboard settings:
```bash
sudo dpkg-reconfigure keyboard-configuration
```

## Installing ROS
Install ROS by using our provided [ROS installation script](https://gist.githubusercontent.com/bugra-derre/2fcfb0b77d94031e7446838f4d4f2084/raw). You could use *wget* to download the script and install:

```bash
cd your/desired/directory
wget -O install_ros_kinetic.sh https://gist.githubusercontent.com/bugra-derre/2fcfb0b77d94031e7446838f4d4f2084/raw
bash install_ros_kinetic.sh
```

## Other stuff to do
In order to make the application run, you need to edit the files
* src/rplidar/launch/rplidar.launch and
* src/hector_slam/hector_slam_launch/launch/rplidar.launch

The file _rplidar.launch_for_hector_slam_ describes how the launch file has to look like for the hector_slam package. The file _rplidar.launch_for_rplidar_ describes the launch file for the rplidar package.