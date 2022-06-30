# 1.install Ubuntu then ROS

1-Download VMware workstation

2-Download Ubuntu OS ISO file

3-Open Vmware Workstation

4-Setup Vmware Workstation

5-Insert the Ubuntu ISO file

6-Select the Ubuntu OS file

7-Setup Ubuntu OS

8-Restart Ubuntu after Installation

9-Welcome to Ubuntu

## Installation ROS

### Configure your Ubuntu repositories

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
Set up your keys
```
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```


### Installation

```
sudo apt update
```

Now pick how much of ROS you would like to install.

Desktop-Full Install: (Recommended) : Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages
```
sudo apt install ros-noetic-desktop-full
```


Desktop Install: Everything in ROS-Base plus tools like rqt and rviz
```
sudo apt install ros-noetic-desktop
```

ROS-Base: (Bare Bones) ROS packaging, build, and communication libraries. No GUI tools.
```
sudo apt install ros-noetic-ros-base
```

There are even more packages available in ROS. You can always install a specific package directly.
```
sudo apt install ros-noetic-PACKAGE
```
e.g.
```
sudo apt install ros-noetic-slam-gmapping
```

### Environment setup
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc

source ~/.bashrc
```
if you use zsh 

```
echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```

### Dependencies for building packages

```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

### Initialize rosdep

```
sudo apt install python3-rosdep
```

With the following, you can initialize rosdep.

```
sudo rosdep init
rosdep update
```
# The output:
```
ali@vm:~$ roscore
... logging to /home/ali/.ros/log/f1747230-f815-11ec-adc7-e95db5452547/roslaunch-vm-6081.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

started roslaunch server http://vm:35981/
ros_comm version 1.15.14


SUMMARY
========

PARAMETERS
 * /rosdistro: Debian
 * /rosversion: 1.15.14

NODES

auto-starting new master
process[master]: started with pid [6088]
ROS_MASTER_URI=http://vm:11311/

setting /run_id to f1747230-f815-11ec-adc7-e95db5452547
process[rosout-1]: started with pid [6097]
started core service [/rosout]
```
![The output](https://user-images.githubusercontent.com/86229247/176577676-101c7d27-9b9e-4dfc-a5ec-ebaeb4695133.png)

