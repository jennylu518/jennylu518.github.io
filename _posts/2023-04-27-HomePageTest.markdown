---
layout:     post
title:      "my first blog page"
subtitle:   ""
date:       2023-04-27 20:00:00
author:     "jenny"
header-img: "img/post-bg-universe.jpg"
tags:
    - test
---
# my first title-1
我的第一个文章。。。。

### title1-1

img

![chrome安装插件后的效果图](/img/in-post/chromenodejs/1.png)


pdf

[mypdf addr](https://github.com/NetEase/pomelo/wiki/pomelo的HelloWorld)

![快捷按钮](/img/in-post/chromenodejs/2.png)
ork targets后边的Configure来进行设置：

![使用Discover network targets设置](/img/in-post/chromenodejs/3.png)

###开始使用chrome来断点调试pomelo服务器
找一个地方先建一个pomelo项目

新建pomelo项目可以参考官方的文档：

[pomelo的HelloWorld](https://github.com/NetEase/pomelo/wiki/pomelo的HelloWorld)

建好项目之后，加好game-server/config/servers.json中我们要调试的服务器参数"args": "--inspect=9229",同时打开chrome浏览器。

![加上--inspect参数](/img/in-post/chromenodejs/4.png)

cd到game-server目录,并运行game-server服务器
```bash
cd game-server
pomelo start
```
服务器启运后，可以看到终端中显示Debugger attached.文字,如下图：

![终端里会显示Debugger attached.](/img/in-post/chromenodejs/5.png)

同时chrome的js调试器也打开了。

![Developer Tools-Nodejs](/img/in-post/chromenodejs/6.png)

点击Sources菜单，可以看到pomole的源码，找到我们服务器的Handler.js文件，在这里打上断点。如下图:

![打上断点的handler.js文件](/img/in-post/chromenodejs/7.png)

这里运行的pomelo的HelloWorld项目，这个项目的客户端是web网页，我先cd到web-server目录，启动客户端的web服务器
```bash
cd web-server
node app.js
```
接下来在浏览器里输入运行web服务器后终端里提示的http地址：

![http服务器地址](/img/in-post/chromenodejs/8.png)

http://127.0.0.1:3001/index.html

打开之后，会看到Welcome to Pomelo的网页，下边有一个Test Game Server的按钮，点了之后，会在chrome中看到断点已被击中。

![断点击后的样子](/img/in-post/chromenodejs/9.png)

上图中的1就是我们断点的位置，2是nodejs的程序调用堆栈。

###总结
用这种方法来调试nodejs服务器程序还是比较方便的。当然了，chrome除了可以调试服务器代码外，调试web客户端那就更不在话下了。

