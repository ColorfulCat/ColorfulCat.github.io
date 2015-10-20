---
layout: post
title: MAC系统下的Eclipse和Android Studio无法识别魅族和小米设备的解决方法
excerpt: "MAC系统下的Eclipse和Android Studio无法识别魅族和小米设备的解决方法,主要测试过魅族MX4"
date: 2015-10-20 11:20:20
categories: Android MAC

---

* content
{:toc}


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
我的魅族MX4在连接MAC系统下的Eclipse或者Android Studio时，device里面无法识别出我的手机，网上找了一圈，一个解决方案，特此记录：

1. 去“关于本机”- “系统报告…” -  选择“USB”选项卡，然后在右侧USB设备树中找到MX4（也就是你的设备）,然后在下方找到MX4的厂商ID ，应该是 `0x2a45` 
2. 打开终端  输入  
 `echo 0x2a45 >> ~/.android/adb_usb.ini`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
按下回车，然后重启一下电脑，就OK了~ 小米貌似也是这样解决的，，

