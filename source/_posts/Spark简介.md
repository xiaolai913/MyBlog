---
title: Spark简介
date: 2016-10-01 20:54:41
categories: 大数据计算
tags: spark
#thumbnail: https://spark.apache.org/images/spark-logo-trademark.png
#banner: https://spark.apache.org/images/spark-logo-trademark.png
---

### Spark是什么？
- 一种快速、通用的大规模数据处理引擎
- 由于spark充分利用的内存计算的特点，也可称作是一种分布式内存计算引擎

### Spark的特点
- 快速：Spark基于内存和并行处理的能力使得它在运行程序时比hadoop MapReduce在内存中计算快100倍，在硬盘数据处理上快10倍??(官方说法，不过大多数场景下的确比Hadoop快不少）
- 通用：**One stack to rule them all! ** 批处理、交互式查询（SQL）、流式计算、机器学习等Spark样样都能做; 不过大规模离线数据处理、交互式查询是他的强项
- 易用：提供了丰富的（80+）分布式数据处理[算子](https://spark.apache.org/docs/latest/programming-guide.html#transformations)来简化用户开发分布式程序的代价；支持Scala、Java、Python、R等语言进行程序开发（首推Scala，毕竟Spark底层是用Scala来实现的）
- 哪都能跑：既可以部署一套单独的Spark集群（即Standalone模式）来跑Spark程序，也可以将Spark程序跑在您现有的Hadoop, Mesos等集群上，甚至还可跑在云上（如Amazon的EC2等）

### Spark的应用实践
- [博文 - Spark在腾讯、雅虎、优酷的成功应用](http://database.51cto.com/art/201406/442055.htm)
- 我们团队目前主要用Spark来进行海量数据的离线计算、以及实时日志/消息数据的分析处理 

### 如何快速上手Spark
- 引言：Spark官网上的各种文档都写得很好通俗易懂，是最好的学习材料；学习Spark贵在实践，好在Spark易用性强且提供了spark shell这个交互式工具来方便用户快速实践各种示例程序
- 学习步骤推荐：
  - 浏览下官网，过一遍官方文档的Quick Start和Spark Programming Guide两小节（附录中的中文文档翻译的不错也是一种选择）
  - 在学习上面文档的过程中，大部分例子代码都可直接在Spark shell命令行下直接操作，有了实践理解起来也会更有感觉（spark环境的搭建可以参看后面的介绍）
  - 如果光看文档觉得不过瘾的话，有时间可以看看小象科技上Spark的学习视频，讲得挺不错的（可以用我朋友的账户免费看哦）
  - 如果想用Scala来开发Spark程序，那么在真正编写Spark程序前可以简单过一遍Scala的语法（入门期不必太精通，基本语法会了就够用了）
  - 接下来就是实践、实践再实践了。可以在Spark官网上下载最新的[Spark源码](https://spark.apache.org/downloads.html)，源码中有个example目录上面放了很多基本的Spark程序示例，可以比着葫芦画瓢试着写几个Spark小程序
  - 搭建Spark开发环境，运行自己的Spark程序
  - Spark的运行环境多样，除了standalone集群模式、Yarn/Mesos等第三方托管运行模式、云上运行模式外，也提供了本地运行模式（伪分布式模式）；初学者可以在自己的机器上安装Spark环境直接运行应用程序
- 进价学习
  - Spark的原理学习：基础论文学习，核心概念RDD的理解，Spark工作机制探究
  - Spark源码分析：官网下载Spark源码，学习各个模块的实现细节
  
### Spark本地运行环境安装
- 先决条件：
  - Linux/类Linux环境（windows的话可以安装个Linux虚拟机，不过还是推荐Linux）
  - JDK 1.7以上，[Scala 2.10.x](http://www.scala-lang.org/)
- 安装步骤
  - [官网](http://spark.apache.org/downloads.html)上下载预编译版spark，如[这一版](http://mirrors.cnnic.cn/apache/spark/spark-1.6.1/spark-1.6.1-bin-hadoop2.6.tgz )
  - 下载解压软件包后，即可通过执行bin目录下的spark-shell即可进入spark交互式编程shell环境
  - 在交互式编程环境下可以一行一行执行Spark程序（交互式环境仅支持用Scala语言），可以试试文档中的各种列子代码哦

### 学习资料
- [官网](https://spark.apache.org/)、[官方文档](https://spark.apache.org/docs/latest/)
- [中文文档](https://endymecy.gitbooks.io/spark-programming-guide-zh-cn/content/)
- [小象科技-Spark课程视频](http://www.chinahadoop.cn/course/114)
- [综述论文](http://www.eecs.berkeley.edu/Pubs/TechRpts/2014/EECS-2014-12.pdf)、[RDD原理论文](https://www.usenix.org/system/files/conference/nsdi12/nsdi12-final138.pdf)
- Scala学习: [Scala开发教程](http://wiki.jikexueyuan.com/project/scala-development-guide/)、[Scala课堂](http://twitter.github.io/scala_school/zh_cn/)
- [BDAS Stack](https://amplab.cs.berkeley.edu/software/): the Berkeley Data Analytics Stack
- [Spark开发环境搭建-Eclipse](http://www.cnblogs.com/simplestupid/p/4687507.html)

### 其他类似引擎/技术
- [Flink](https://flink.apache.org/)：类Spark的通用计算引擎，强在流式计算；[中文文档](http://doc.flink-china.org/)
- [Storm](http://storm.apache.org/)：流式计算引擎
