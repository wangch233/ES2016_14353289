# 关于DOL的描述

###*分布式操作层（DOL）是一个程序的并行应用软件开发框架。DOL允许指定应用基于计算Kahn进程网络模型的应用范围以及基于SystemC仿真引擎的特征。此外，Dol提供了基于XML规范的格式来描述一个多处理器系统上的并行应用程序的实现，包括结合和映射。

###*分布式系统（distributed system）是建立在网络之上的软件系统。正是因为软件的特性，所以分布式系统具有高度的内聚性和透明性。因此，网络和分布式系统之间的区别更多的在于高层软件（特别是操作系统），而不是硬件。内聚性是指每一个数据库分布节点高度自治，有本地的数据库管理系统。透明性是指每一个数据库分布节点对用户的应用来说都是透明的，看不出是本地还是远程。在分布式数据库系统中，用户感觉不到数据是分布的，即用户不须知道关系是否分割、有无副本、数据存于哪个站点以及事务在哪个站点上执行等。
#DOL的安装过程

##1.安装一些必要环境：

###$	sudo apt-get update

![](1.1.jpg)

###$	sudo apt-get install ant

![](1.2.jpg)

###$ 	sudo apt-get install openjdk-7-jdk

![](1.3.jpg)

###$	sudo apt-get install unzip

![](1.4.jpg)


##2.下载文件


###sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz

###sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip

##3.解压文件

###新建dol的文件夹 

###$	mkdir dol

###将dolethz.zip解压到 dol文件夹中

###$	unzip dol_ethz.zip -d dol

###解压systemc

###$	tar -zxvf systemc-2.3.1.tgz

##4.编译systemc

###解压后进入systemc-2.3.1的目录下

###$	cd systemc-2.3.1

###新建一个临时文件夹objdir

###$	mkdir objdir

###进入该文件夹objdir

###$	cd objdir

###运行configure(能根据系统的环境设置一下参数，用于编译)

###$	../configure CXX=g++ --disable-async-updates


![](3.1.jpg)

![](3.2.jpg)

##5.编译systemc

###$	sudo make install

![](4.1.jpg)


##6.记录当前的工作路径
###$	pwd

![](5.1.jpg)

##7.编译dol

###$	ant -f build_zip.xml all

![](7.1.jpg)

![](7.2.jpg)

###进入build/bin/mian路径下

###$	cd build/bin/main

###然后运行第一个例子

###$	ant -f runexample.xml -Dnumber=1

![](7.3.jpg)

![](7.4.jpg)

#实验感想

###这次属于配置实验，难度其实不大，本来以为可以按照ppt顺利的完成，但是在配置时，还是出现了不小的问题，明明按照步骤一步步来，结果还是不行，最后一步显示 g++。。。。。。。。等等，有问题，重装之后也不能解决，后来实在没办法，只有重新装ubantu，好在重装之后解决掉了



