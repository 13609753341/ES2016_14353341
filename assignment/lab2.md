#一、实验步骤
##1、修改example1,使得3个square模块变成2个；

###在example1中找到square.c文件，将里面原来value=“3”改成“2”即可，在这个程序中，name=“N”及时整个程序的总长度为2，因此某块也即是2个，具体截图请查看实验结果：

![http://i1.piimg.com/567571/f7c304f0360202d4.png](http://i1.piimg.com/567571/f7c304f0360202d4.png)
##2、修改example2，使其输出3次方数；

###在example2中找到xml文件，将原来的i * i改成i * i * i即可：

![http://i1.piimg.com/567571/a4fcdb4ec763f39b.png](http://i1.piimg.com/567571/a4fcdb4ec763f39b.png)

##3、在修改完这些文件之后，只需要再次运行这些文件即可查看实验结果：

###sudo ant -f runexample.xml -Dnumber==1;

###sudo ant -f runexample.xml -Dnumber==2;

#二、实验结果


 generator enerator enerator enerator 生成 0~19 的整数的三次方：


![http://p1.bpimg.com/567571/f03bda4aaaa519f7.png](http://p1.bpimg.com/567571/f03bda4aaaa519f7.png)

各进程功能定义与 example1example1example1 example1相同，不之处在于 example2example2example2 example2架构中包含 3个 square square进程，故结果为 i4：

![http://p1.bpimg.com/567571/317edfe0e3e369ef.png](http://p1.bpimg.com/567571/317edfe0e3e369ef.png)
![http://p1.bpimg.com/567571/bb39ac778eb4667a.png](http://p1.bpimg.com/567571/bb39ac778eb4667a.png)
![http://p1.bpimg.com/567571/057b29aa8d4209a9.png](http://p1.bpimg.com/567571/057b29aa8d4209a9.png)

#三、实验感想

###生产者消费者问题（Producer-consumer problem），也称有限缓冲问题（Bounded-buffer problem），是一个多线程同步问题的经典案例。该问题描述了两个共享固定大小缓冲区的线程——即所谓的“生产者”和“消费者”——在实际运行时会发生的问题。生产者的主要作用是生成一定量的数据放到缓冲区中，然后重复此过程。与此同时，消费者也在缓冲区消耗这些数据。该问题的关键就是要保证生产者不会在缓冲区满时加入数据，消费者也不会在缓冲区中空时消耗数据。

###在本次实验中还有一些小问题，如出现权限不够，则需要加sudo，运行完的文件会自动存放到build文件中，如果需要运行文件并且保存，则需要将原来build文件中的内容删除；

![http://p1.bqimg.com/567571/918343852fa386b8.png](http://p1.bqimg.com/567571/918343852fa386b8.png)
