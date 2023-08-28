# slam_in_autonomous_driving_notes

高博的新书SLAM in Autonomous Driving book (SAD book)和深蓝学院课程《自动驾驶中的slam技术》第一期的课程笔记

注：本项目为开源项目，不作商业用途，仅个人学习记录，为保护高翔老师的版权和其他权利，使用者需要在[https://github.com/gaoxiang12/slam_in_autonomous_driving/tree/master](https://github.com/gaoxiang12/slam_in_autonomous_driving/tree/master)
的license的基础上进行开发和使用。

# 一、课程简介

此课程以激光slam为主，[高翔老师](https://github.com/gaoxiang12)的新书，[深蓝学院搭配课程《自动驾驶中的slam技术》第一期](https://www.shenlanxueyuan.com/my/course/615)

课程代码：[https://github.com/gaoxiang12/slam_in_autonomous_driving/tree/master](https://github.com/gaoxiang12/slam_in_autonomous_driving/tree/master)

这个库是在学习课程过程中的笔记。计划包括思维导图笔记，相关证明与程序运行记录（不提供课程作业答案）

**优秀学员证书：**

![优秀学员证书]([https://github.com/gaoxiang12/slam_in_autonomous_driving/tree/master](https://github.com/Longxiaoze/slam_in_autonomous_driving_notes/blob/main/imgs/graduation.png))

# 二、代码安装

**系统：ubuntu20**

参考页面：[https://github.com/gaoxiang12/slam_in_autonomous_driving/tree/master](https://github.com/gaoxiang12/slam_in_autonomous_driving/tree/master)

## 2.1安装步骤：

**（1）安装ubuntu20系统（新的系统从0开始快速安装）**

**（2）c++环境及其他基础工具**

```plain
sudo apt update
sudo apt upgrade
sudo apt install build-essential
sudo apt install git
sudo apt install wget
gcc -v  # gcc version 9.4.0
```
**（3）ros-****Noetic****环境**（课程和代码不使用ros相关知识，只是编译和运行代码需要）
下面是我学习ros的时候遇到的工具，来自鱼哥。

```plain
wget http://fishros.com/install -O fishros && . fishros
```
依次选择：【1】一键安装:ROS --> 【1】更换系统源再继续安装(国内)/【2】不更换继续安装(国外) --> 【1】[1]:noetic(ROS1) 
即可安装ros-Noetic

**（4）ros的其他依赖**

```plain
sudo apt install -y ros-noetic-pcl-ros ros-noetic-velodyne-msgs libopencv-dev libgoogle-glog-dev libeigen3-dev libsuitesparse-dev libpcl-dev libyaml-cpp-dev libbtbb-dev libgmock-dev
```
**（5）Pangolin安装（自行选择安装路径）**
```plain
git clone --recursive https://github.com/stevenlovegrove/Pangolin.git
cd Pangolin
./scripts/install_prerequisites.sh recommended
cmake -B build
cmake --build build
sudo make install
sudo ldconfig # 来自助教的解决，不做这个操作后面会报错
```
**（6）slam_in_autonomous_driving及g2o编译运行**
**g2o：（路径自行安装）**

```plain
git clone https://github.com/gaoxiang12/slam_in_autonomous_driving.git
cd slam_in_autonomous_driving/
cd thirdparty/g2o/
mkdir build
cd build/
cmake ..
make -j4
```
手动操作：（在thirdparty/g2o/的文件夹中搜索config.h文件，将config.h文件放在thirdparty/g2o/路径下）
**slam_in_autonomous_driving编译：**

```plain
cd slam_in_autonomous_driving/
mkdir build
cd build/
cmake ..
make -j4
```
至此不报错的话编译结束。
**slam_in_autonomous_driving运行：**

编译生成的所有可执行文件在slam_in_autonomous_driving/bin/文件夹中

运行时需要在slam_in_autonomous_driving/目录下，在此处新建一个名为dataset的文件夹，将提供的数据集放在这个文件夹中，最终数据集的目录结构slam_in_autonomous_driving/dataset/sad/2dmapping

# 三、更新记录

TODO:在这里写更新的记录

|时间|章节|笔记|代码|备注|
|:----|:----|:----|:----|:----|
|2023.05.13|00_源码安装|readme.md|---|源码安装的步骤|
|2023.05.28|第1章: 自动驾驶概述、基础数学知识回顾|01.md|---|更新了做第一章节作业时的参考网站|
|    |    |    |    |    |
|    |    |    |    |    |
|    |    |    |    |    |
|    |    |    |    |    |
|    |    |    |    |    |
