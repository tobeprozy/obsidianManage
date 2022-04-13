# 一、学习网站
http://wiki.ros.org/ROS/Tutorials

# 二、ROS安装过程

![[Pasted image 20220409200506.png]]
![[Pasted image 20220409200537.png]]
### Setup your sources.list

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
    
### Set up your keys
```
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add 
```
### Installation

First, make sure your Debian package index is up-to-date:

```sudo apt update```

### **Desktop-Full Install: (Recommended)**

```sudo apt install ros-noetic-desktop-full```

安装失败可能需要输入一下命令：
```
sudo apt update --fix-missing
```

There are even more packages available in ROS. You can always install a specific package directly.

```apt install ros-noetic-slam-gmapping```

To find available packages, see [ROS Index](https://index.ros.org/packages/page/1/time/#noetic) or use:

```apt search ros-noetic```

### Environment setup
You must source this script in every **bash** terminal you use ROS in.

```source /opt/ros/noetic/setup.bash```

```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
### Dependencies for building packages
To install this tool and other dependencies for building ROS packages, run:

```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```
Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS

```sudo apt install python3-rosdep```

With the following, you can initialize rosdep.

```
sudo rosdep init
rosdep update
```
# 三、ROS IDE
## [官方网站](http://www.roboware.me/#/home)不太好进
roboware相当于一个专门适配ROS的vscode，功能性十分强大，几乎所有与ROS相关的操作都可以在IDE中完成。目前官网已经挂掉，可以选择百度云安装：
https://pan.baidu.com/s/1D169dFyf2OD3SFBZVZy3pQ密码：3iuk
或者去github上下载安装。
地址：[github Roboware][https://github.com/TonyRobotics/RoboWare]
![[Pasted image 20220409215236.png]]

1.为了支持Python调试功能，需要安装pylint：

```bash
sudo apt-get install python3-pip
sudo python3 -m pip install pylint
```

如果出现问题,可能是安装源的问题：
```pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pylint```

2.为了获得更好的代码阅读体验，自动格式化整理代码，需要安装clang-format

```sudo apt-get install clang-format```

3.将下载好的压缩包移到一个文件夹里面，在该文件夹里打开终端


在这个目录下，打开terminal

![[Pasted image 20220409220442.png]]
输入：

```sudo dpkg -i roboware-studio_1.1.0-1514335284_amd64.deb   #下载的版本号```
![[Pasted image 20220409220719.png]]
最后发现unbuntu20.04，始终打不开，使用

```
sudo apt --fix-broken install
```
也打不开

网上说20.04不支持roboware
# 四、注意事项
linux 有两种安装方式：
1.sudo apt....之类的，二进制方式，这种是没有源代码的
2.另一种是源代码安装，需要编译make,sudo make install


