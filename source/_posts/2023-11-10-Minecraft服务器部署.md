---
title: Minecraft服务器部署
date: 2023-11-10 08:32:24
tags: 
- linux
- 网络
categories: 计算机/折腾 
---

购买了一台阿里云的ECS，故尝试在服务器上部署Minecraft服务器
<!--more-->

阿里云ECS
Ubuntu22.04
FinalShell

https://www.minecraft.net/zh-hans/download/server
https://minecraft.fandom.com/wiki/Tutorials/Setting_up_a_server

### 1.java环境安装
官方推荐安装OpenJDK 8及更高版本。试着根着官方文档下载OpenJDK 8，发现无法启动。故选择OpenJDK 18，经测试能成功启动。

``` sh
sudo apt update
#更新
sudo apt-get install openjdk-18-jdk-headless
#中间数字是版本号。去掉命令中的“-headless”可以安装完整的Java。
```


### 2.Minecraft服务器端安装与运行
先创建MC专用文件夹，用于存放服务端文件，如minecraft_server本体以及地图资源文件等。
``` bash
mkdir Minecraft
cd Minecraft
```

根据官网上给的minecraft_server.1.20.2文件，直接使用网址下载。
``` sh
wget https://piston-data.mojang.com/v1/objects/5b868151bd02b41319f54c8d4061b8cae84e665c/server.jar
```

然后启动即可
``` bash
java -Xmx1024M -Xms1024M -jar minecraft_server.1.20.2.jar nogui
```


### 3.端口
如果无法联机，可以查看端口是否开放。
Minecraft默认端口是25565，可以通过该端口扫描网址查询端口是否开放：http://www.jsons.cn/port/
也可以自行修改端口。

### 4.Docker
Docker可以大幅简化Minecraft服务器部署流程。这部分下次再写。


<details>
<summary>2333</summary>

23333

</details>