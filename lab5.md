#一、实验原理
    1、SLAM：simultaneous localization and mapping

    2、同时定位与建图；

    3、使用的方法：激光雷达（例如：google的cartographer）;或者摄像头（单目、双目）

    4、ROS上有很多SLAM算法以及数据集；

    5、Robot Operation System,一套框架，底层提供硬件驱动，软件层面支持通用的文件格式；它可以在pc上控制机器人的各个组件。ROS系统由多个各自独立的节点（组件）组成，并且各个节点之间可以通过发布消息模型进行通信。它可以运行在不同的系统、平台、甚至是不同的架构中。

    6、Cartographer是功能非常全面的地图插件,可以实现在pc上动态得观看3D效果的物体（机器），也可以实时了解周边的地理位置动态。Cartographer，是Google开源的一个ROS系统支持的2D和3D SLAM（simultaneous localization and mapping）库。

    SLAM 算法结合来自多个传感器（比如，LIDAR、IMU 和 摄像头）的数据，同步计算传感器的位置并绘制传感器周围的环境。例如，使用该方法绘制住室的平面图：
#二、实验步骤
    1、ubuntu的版本不同，安装ROS的指令也不同，我的ubuntu为14.04，则：
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu lucid main" > /etc/apt/sources.list.d/ros-latest.list'

![http://yotuku.cn/link?url=4kF3J9RlM&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118](http://yotuku.cn/link?url=4kF3J9RlM&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118)

    2、设置Key，把ROS源的Key加入本地信任列表：wget http://packages.ros.org/ros.key -O - | sudo apt-key add -

    3、确保软件包列表是最新的：sudo apt-get update

    4、 环境变量的设置：source /opt/ros/fuerte/setup.bash

    5、安装脱机工具：sudo apt-get install python-rosinstall python-rosdep

    6、在ROS上安装cartographer：

    sudo apt-getupdate

    sudo apt-getinstall -y Python-wstool python-rosdep ninja-build

    mkdir catkin_ws

    cd catkin_ws

    wstool init src

    wstool merge -    tsrchttps://raw.githubusercontent.com/googlecartographer/cartographer_ros/master/cartographer_ros.rosinstall
wstool update -tsrc

    rosdep update

![http://yotuku.cn/link?url=N1od7cClM&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118](http://yotuku.cn/link?url=N1od7cClM&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118)


    rosdep install--from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y

    catkin_make_isolated --install --use-ninja

    isolated --install --use-ninja

    source install_isolated/setup.bash

#三、实验结果
![http://yotuku.cn/link?url=EyjkWcAef&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118](http://yotuku.cn/link?url=EyjkWcAef&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118)

![http://yotuku.cn/link?url=4J8plcAgz&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118](http://yotuku.cn/link?url=4J8plcAgz&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118)

![http://yotuku.cn/link?url=EkeYlcClM&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118](http://yotuku.cn/link?url=EkeYlcClM&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111118)
#四、实验感想

    本次实验对于电脑的配置要求比较高，有些指令本身需要跑比较长时间，但是如果一直卡在原地那也证明是安装不成功的，ppt上的安装教程是英文的，很多指令不是很理解，所以找了一个中文版的安装教程：
http://blog.csdn.net/xiaocainiaoshangxiao/article/details/13288515；

    对于ROS的了解： ROS是开源的，是用于机器人的一种后操作系统，或者说次级操作系统。它提供类似操作系统所提供的功能，包含硬件抽象描述、底层驱动程序管理、共用功能的执行、程序间的消息传递、程序发行包管理，它也提供一些工具程序和库用于获取、建立、编写和运行多机整合的程序。ROS的运行架构是一种使用ROS通信模块实现模块间P2P的松耦合的网络连接的处理架构，它执行若干种类型的通讯，包括基于服务的同步RPC（远程过程调用）通讯、基于Topic的异步数据流通讯，还有参数服务器上的数据存储。但是ROS本身并没有实时性。
   
![http://yotuku.cn/link?url=NksYr50eG&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111119](http://yotuku.cn/link?url=NksYr50eG&tk_plan=free&tk_storage=tietuku&tk_vuid=6a04ec2c-0484-4cde-8c50-857fe53b269c&tk_time=2016111119) 

