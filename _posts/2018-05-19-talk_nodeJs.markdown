---
layout:     post
title:      "聊聊NodeJs"
subtitle:   " \"聊聊NodeJs\""
date:      2018-05-13 23:55:12 
author:     "xiaobai"
header-style: text
catalog: true
tags:
    - 程序世界
     
---

从去年下半年开始公司pc端开始使用nodeJS作为中间层转发服务应用。刚开始只是知道nodejs这个名词，并没有深刻理解，老大搭建好，自己就这么用了。后来慢慢的看资料学习，才逐渐的理解。今天自己再梳理一遍，也许有其他的发现。

  

###   

-   **nodeJs是什么**

  

JS是脚本语言，脚本语言都需要一个解析器才能运行。对于写在HTML页面里的JS，浏览器充当了解析器的角色。而对于需要独立运行的JS，**NodeJS就是一个解析器。**

**Node.js是一项服务器技术。**

每一种解析器都是一个运行环境，不但允许JS定义各种数据结构，进行各种计算，还允许JS使用运行环境提供的内置对象和方法做一些事情。例如运行在浏览器中的JS的用途是操作DOM，浏览器就提供了`document`之类的内置对象。**而运行在NodeJS中的JS的用途是操作磁盘文件或搭建HTTP服务器，NodeJS就相应提供了`fs`、`http`等内置对象。**

![](https://img-blog.csdn.net/20180519183512497?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjg1MjIzNQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "Click and drag to move")​

  

###   

-   **Node.js的优点？Node.js的缺点？**

  

Node.js的诞生很大程度上归功于v8引擎的出现。v8引擎是由Google推出的，为其浏览器Chrome所设计的开源JavaScript引擎。

  

这就是Nodejs。(一个提供了一些编程接口，运行在Google V8 JavaScript引擎上的平台)，所以JavaScript可以直接运行在nodejs上（自带了v8引擎）。

**a=>****优点：**

①更好的组织代码，提升复用性。当然在ES6中这一点也得到了很大的提升。

②处理文件与数据库。

③与互联网进行沟通，以标准化的格式处理请求并发送回答。

  

④Node.js最大的特点就是非阻塞异步式I/O和事件驱动，对于高并发的解决方法，Node.js摒弃了传统的多线程模型，

使用的是单线程模型，对所有的I/O请求都采用异步式请求的方式；

  

Node.js适合应用在高并发、I/O密集、少量业务逻辑的场景

说说nodeJS的eventLoop:

请看下面的示意图（作者[@BusyRich](https://twitter.com/BusyRich/status/494959181871316992)）。

![](https://img-blog.csdn.net/20180519175722180?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjg1MjIzNQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "Click and drag to move")​

  

  

（1）V8引擎解析JavaScript脚本。

（2）解析后的代码，调用Node API。

（3）[libuv库](https://github.com/joyent/libuv)负责Node API的执行。它将不同的任务分配给不同的线程，形成一个Event Loop（事件循环），以异步的方式将任务的执行结果返回给V8引擎。

（4）V8引擎再将结果返回给用户。

  

先执行主线程里的任务，如果主线程的任务执行完毕，则看异步队列中是否有任务，如果有则将任务放入主线程中执行.

**b=>缺点：**

无法满足实时密集型请求处理。

这是对node的一些基本了解，你得知道它是干什么的，才能更好的去应用它。目前，公司在pc端使用node+express做中间层的转发，达到了更好的前后端分离,提高性能。

下次再讲下基于session的登录认证。

再次按照目录梳理，只是为了自己更深刻的理解。目前这里的文章还是总结为主，希望后面自己能完全用自己的语言写出来。继续加油~~

  

参考文章：

[https://www.w3cschool.cn/fjvyha/jxkgsozt.html](https://www.w3cschool.cn/fjvyha/jxkgsozt.html)

[http://www.ruanyifeng.com/blog/2014/10/event-loop.html](http://www.ruanyifeng.com/blog/2014/10/event-loop.html)







