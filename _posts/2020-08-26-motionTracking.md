---
layout: post
title: Vicon动作捕捉系统评测
date: 2020-08-26
Author: Chaosikaros
tags: [动作捕捉]
comments: true
toc: true
pinned: true
---
今天有幸接触到了Vicon的一套动作捕捉系统，Vero V2.2。报价貌似三四十万，主要的硬件是八台红外动作捕捉相机，每一台都能买辆车了。参数如下。

Parameters: Max HZ = 330, Max resolution = 2.2M pixels, 

Horizontal FOV = 98.1°, Vertical FOV = 50.1°.

Min. number of cameras = 2.

配了一个交换机，相机用带供电的网线和交换机连接再连到电脑上。

原理看似很简单，就是把一些涂有反光材料的小球贴到被追踪物体上，相机镜头外有一圈红外LED，中间的红外相机就能看到小球反射的光。把画面发给电脑来计算位置，配置上要求独立显卡，那估计是用到显卡来运算了，也可能是配套软件要求独立显卡。听供应商的人讲，严格的暗室实验环境下精度能到0.01mm，一般使用好像只有0.xmm。

这套系统的优点是高精度高帧率，和一系列配套的软件。

Nexus: designed for life sciences: automated features, intelligent processing and flexible controls.

Shōgun: designed for Visual effects (VFX). For media and entertainment applications.

Evoke: designed for location based VR (LBVR).

Tracker: designed for high precise tracking.

ProCalc: visual application for creating custom kinematic models.

Vicon Control: mobile app for system control and capture.

Supported game engines: Unreal Engine, Unity3D and so on.

Datastream SDK: for MATLAB, Labview, C++ and .Net.

缺点除了垄断行业带来的虚高价格外（定位的塑料小球一个200元，某宝20），其他缺点也不少。首先是定位球多的话，因为遮挡而丢失的数据就会增加。官方的配套软件能在录制完后进行手动的数据补全，可以根据其他定位球的前后轨迹来计算被遮挡住的球的位置。

定位球摆放上需要尽量摆成一个面，这样丢失点的话，容易计算。定位球有不同的大小，可以贴到嘴唇上读唇，也可以贴到身上，无人机上。软件上，主要的软件Nexus只支持windows，系统界面设计和建模软件差不多。

供应商给看了很多例子，电影游戏动画，机器人，步态分析等等。看无人机例子的时候想到了网上tango的无人机定位应用，也很稳。但后来我用tango做小型无人车定位时却很容易遇到漂移，可能是因为我用的是阉割版。想起来最近有个依靠深度学习加点云避障的无人机看上去也很稳。红外定位球的动作捕捉，和这类点云SLAM的最大区别还是精度和帧率吧。红外定位球的摆放数量几乎不受限制，每台相机最远追踪距离是十米，而且可以摆放多个相机。小型化无需外置传感器的高精度定位还是有不少应用场景，比如最近几年的各种VR、MR一体机。如果这类定位技术能低成本量产，精度和帧率提上去的话，或许能取代红外动作捕捉的部分应用场景。 

当初采购的时候我还对比了一下Advanced Realtime Tracking的ARTTRACK5，做红外动作捕捉的还有别的公司，ART就是其中之一。不过ART的配置略逊一筹，软件支持上没有Vicon多，ART就只支持Unity，Vicon还支持虚幻。但这两个公司的定位上是有些差异的，Vicon给的应用例子大多还是电影游戏为主，说起动作捕捉，一般人可能也就只会想到电影和游戏吧。ART给了一些航空航天和汽车制造行业的例子。Vicon的工学例子大多是无人机和机器人。

对于一般人来说，这套系统的最大用途可能是VR全身动作捕捉，这套系统的定位延迟据称是比一般的VR低。但成本还是太高了，Kinect也能做动作捕捉，价格可能只相当于Vicon的几个定位球。Kinect也能串联避免盲区，可是Kinect的大部分应用可能都没有支持串联。这套系统对于一般人来说最大的用途应该只是更精准的VR全身动作捕捉，高质量Vtuber。

面部表情和身体动作捕捉也有不少廉价的替代方案，把tango玩死后苹果又开始进军深度相机，unity官方就有一个用iphone前置深度相机录制面部表情动画的例子，除了精度和帧率比不如红外动捕外，剩下的就几乎都是优点。深度相机和一般相机的身体动作捕捉方案也有不少。但还是在精度和帧率上打不过红外动捕，这也正是红外动捕用户的最大需求。