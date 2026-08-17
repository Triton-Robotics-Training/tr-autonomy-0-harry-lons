[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/8SCdojev)
# TR-Autonomy-0
Setup guide for TR Autonomy recruits

[![Autonomy Training Resources](https://img.shields.io/badge/CV-%20Training%20Resources-eac817?labelColor=2a77a2&style=for-the-badge)](https://github.com/Triton-Robotics-Training/TR-CV-0/blob/main/resources.md)

Congratulations and welcome to the Autonomy team! Before we can jump into coding, we need to setup our environment first.
To run our code in TR, you need at least 2 things: **Ubuntu** and **ROS2**
- **Ubuntu** is a Distro that runs on Linux, which is a type of Operating System.
- **ROS2** (Robot Operating System) is a combination of software libraries to develop robotics projects, best run on ubuntu.

We recommend setting up Ubuntu either by simulating it through a Virtual Machine or through Dual Boot. Here are a couple of the tradeoffs of each:
- **Virtual Machine** tends to be slower than Dual-Boot due to simulating a second machine on your current machine. But it is safer, and much less likely to mess up your machine.
- **Dual-Boot** involves downloading a second operating system that you can switch between on starting up your computer. It is fast, but can be bad if you mess it up and is hard to setup on Mac devices.

### Make sure to install these versions: Ubuntu 22.04 and ROS2 Humble

## Installing Ubuntu

### Dual Boot (for x86 only):
Here's a pretty good guide on installing Ubuntu: https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview  
And one that uses Rufus if BalenaEtcher isn't working: https://www.onlogic.com/blog/how-to-dual-boot-windows-11-and-linux/

### Virtual Machine (Survivable):
#### For x86:
[VirtualBox](https://www.virtualbox.org/)

[VMWare Player](https://www.vmware.com/products/workstation-player.html)
#### For Apple Silicon (M-series Macs):
[UTM](https://mac.getutm.app/)

![image](https://github.com/user-attachments/assets/d016f46f-20be-4a36-b850-1a947bf13c19)
Example of a running version of Ubuntu

## Installing ROS2
Once you have a running Ubuntu install, follow these directions to install ROS2 Humble (I recommend the Desktop Install): [https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html  ](https://docs.ros.org/en/humble/Installation.html). Alternatively, you can just copy and paste the commands below.

Make sure to install using the debian packages, __not from source__! (Recommend desktop install, which are the commands below).

```bash
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```

```bash
sudo apt install software-properties-common
sudo add-apt-repository universe
```

```bash
sudo apt update && sudo apt install curl -y
export ROS_APT_SOURCE_VERSION=$(curl -s https://api.github.com/repos/ros-infrastructure/ros-apt-source/releases/latest | grep -F "tag_name" | awk -F'"' '{print $4}')
curl -L -o /tmp/ros2-apt-source.deb "https://github.com/ros-infrastructure/ros-apt-source/releases/download/${ROS_APT_SOURCE_VERSION}/ros2-apt-source_${ROS_APT_SOURCE_VERSION}.$(. /etc/os-release && echo ${UBUNTU_CODENAME:-${VERSION_CODENAME}})_all.deb"
sudo dpkg -i /tmp/ros2-apt-source.deb
```

```bash
sudo apt update
sudo apt upgrade
```

```bash
sudo apt install ros-humble-desktop
```

If you can get a publisher and a talker running in terminal, congratulations! You've just setup your environment. Just make sure to take a screenshot of ubuntu and commit it to your work of this repository. Before you move on to week 1, we now recommend:
- brushing up on C++ ([link](https://www.learncpp.com/))
- reading the ROS2 humble [documentation](https://docs.ros.org/en/humble/Tutorials.html)
- setting up your preferred IDE  

More resources can be accessed by clicking the "CV Training Resources badge" at the top of the README to see the relevant chapters.
**To complete this assignment, take a screenshot of ubuntu running, add it to this git repo, and commit+push it.**
