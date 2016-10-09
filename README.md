#一、DOL框架描述
分布式操作层（DOL）是一个程序的并行应用软件开发框架。DOL允许指定基于计算Kahn进程网络模型的应用范
围和特点，基于SystemC仿真引擎。此外，劳工部提供了基于XML规范的格式来描述一个多处理器系统上的并行应用程序的实现，包括结合和映射。

Distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

![](http://i1.piimg.com/567571/d463c3b9f8ec3b3c.png)
#二、DOL安装笔记
##1、使用虚拟机VM安装Ubuntu：
   [VMWARE教程](http://jingyan.baidu.com/article/0320e2c1ef9f6c1b87507bf6.html)

   [Ubuntu下载](http://www.ubuntu.com/download/desktop)
##2、安装必要的环境ubuntu：
sudo apt-get update

sudo apt-get install ant

sudo apt-get install openjdk-7-jdk

sudo apt-get install unzip
##3、下载文件：
[sudo wget](http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz)

[sudo wget](http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip)
##4、解压文件
（1）新建dol的文件夹：$sudomkdirdol

（2）将dolethz.zip解压到dol文件夹中：$sudounzip dol_ethz.zip -d dol

（3）解压systemc：$sudotar -zxvfsystemc-2.3.1.tgz
##5、编译systemc
（1）解压后进入systemc-2.3.1的目录下：$cd systemc-2.3.1

（2）新建一个临时文件夹objdir：$sudomkdirobjdir

（3）进入该文件夹objdir：$cd objdir

（4）运行configure(能根据系统的环境设置一下参数，用于编译)

 $sudo../configure CXX=g++ --disable-async-updates
 ![](http://p1.bpimg.com/567571/ef1b4734dbd07318.png)

（5）编译：$sudomake install

（6）记录当前的工作路径(会输出当前所在路径，记下来，待会有用)：$sudopwd
##6、编译dol
（1）进入刚刚dol的文件夹：$cd ../dol

（2）修改build_zip.xml文件

（3）然后是编译：$sudoant -f build_zip.xml all

（4）如果成功则会显示：build successful

![](http://i1.piimg.com/567571/f2c3aa6236cc04b0.png)

#三、实验感想
在本次试验中，我最大的体会是电脑配置一定要好（否则就是自身能力要硬）。因为电脑配置等问题，在使用虚拟机配置ppt上给出的命令行的时候，出现的第一个问题就是下载安装包的速度很慢，甚至晾着电脑一天了还没get全，后来在实验课上跟TA反应了这个问题，TA将我虚拟机上的下载源换了个地址，就可以很顺利地完成下载和安装必要的工具了。

其次就是很多指令需要在命令行中进入到该文件中才能运行否则会出现错误说找不到文件；其次就是很多指令要求管理者身份（需要权限），因此在ppt上的很多指令前需要加上sudo来获取权限（经历就是如果按照ppt上的指令写出来报错说没有找到文件，就要注意是不是没有用命令行进入到该文件的里面；如果报错但不是文件找不到那可能就是没有权限了，基本上加个sudo就可以搞定。