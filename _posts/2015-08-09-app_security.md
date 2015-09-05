---
layout: post
title: APP安全预警
excerpt: "警报！前方高能！有人在说APP的安全问题，其实他就是在装B~~~"
date: 2015-08-09 12:34:56
categories: security APP

---

* content
{:toc}


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;随着移动互联网的概念在生活中不断普及，换句话说，就是越来越多的人们得了“不用智能手机就会死”的毛病~ 甚至已经严重到滋生了一个新的种族：**低头族**。与此同时，为了响应所谓的“大数据时代”的来临，各种设备都在“光明正大”地获（窃）取用户的各种信息。一种获取信息的方式就是应用内部的用户数据录入和采集，这种方式我们也无可奈何，因为周瑜打黄盖--一个愿打，一个愿挨；第二种获取方式，其实就是货真价实的窃取了，一些不法分子通过一些特殊手段去获取用户信息，包括各种程序内数据信息、短信、电话记录、SD卡中的文件和数据等等，这里面或多或少都有一些涉及到用户隐私甚至财产的信息，这些信息如果被不法分子拿到手，后果真的不堪设想。下面举一个例子：

**WhatsApp引出的隐私泄漏风险**

***&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;去年（14年）3月份被Facebook收购的WhatsApp可谓是不太平。安全服务厂商DoubleThink公司14年3月13号称，Android版WhatsApp中存在加密漏洞，允许另一应用访问并读取所有用户的聊天记录。尽管WhatsApp对Android版本进行了大的更新，但该漏洞仍然存在。导致漏洞的是因为Android版的WhatsApp聊天记录被存储在手机上的SD卡内，只要用户授权其他应用访问这些数据，这些聊天记录即可被任何Android应用读取。***

		

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Android的SD卡存储在 /sdcard 目录，仔细观察该目录权限设置，发现SD卡权限是777，也就是说，任何APP都可以读取其他APP保存在SD卡的文件。联系到前文说到恶意软件那么多，保存在SD卡的用户敏感文件就很危险了。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;而去年的的315晚会里所曝光的大唐神器，就是这么一个会盗取用户隐私数据的“神器”。一旦你的Android手机连接上这个神器，就会被强制安装上各种恶意APP，这些APP利用诸如上文WhatsApp的信息泄漏漏洞，来盗窃你手机上的隐私数据。而大唐神器仅仅是冰山一角，根据手机管家的报告：在Android上截获的木马中，超过15%会去窃取用户手机中的隐私。

**那么我们该如何保护我们的APP数据呢？**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*1.将数据库和敏感信息文件存入手机私有目录*


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Android系统的安全模型告诉我们：在默认权限下，任何 APP都无法窃取其他APP私有存储区域的任何数据，谈何隐私窃取。因此，简单的将隐私数据从SD卡移入到APP的私有存储区域即可基本的解决隐私泄漏风险。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;不过这个简易的解决方案，却存在以下几个问题：

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ROOT风险：在已ROOT的Android手机中，任意APP只要取得了ROOT权限，就可以绕过Android的安全模型，随意读写任何数据。而根据DCCI的数据，超过了20%的Android手机都已经被ROOT手机内置存储空间有限：鉴于Android系统的设计，APP的私有存储区域位于手机内置存储中。而大多数的手机内置存储空间很有限，无法存下庞大的图片或者视频文件。隐私数据往往迫不得已被放到不受保护的SD卡中。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*2.加密这些隐私数据*

在敏感数据存入数据库或者文件之前，对其进行加密，需要从数据库中取出使用前，再对其进行解密。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这个解决方案能解决隐私信息保护的问题，但是却给APP带来了可观的修改成本。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*3.利用虚拟文件磁盘：IOCipher*

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;准备下一篇文章来写这个[**IOCipher**](https://guardianproject.info/code/iocipher/)，敬请期待~~~

 