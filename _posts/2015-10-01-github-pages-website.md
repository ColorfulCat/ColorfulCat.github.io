---
layout: post
title: 用Github Pages搭建个人静态网站
excerpt: "用Github Pages搭建个人静态网站，逼格than逼格~"
date: 2015-10-01 10:10:56
categories: Git web

---


* content
{:toc}




##初衷

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
最近一直在折腾前端的东西，然后还把自己平时收集的Android开发过程中使用到的一些资源博文的导航做成了一个静态站点（用的新浪SAE）发布了出去（[AndroidCat](http://www.androidcat.com/)）, 得到了一些小伙伴的认同，也有一些小伙伴说也想搭建一个自己的网站，于是我想着把Github这个（全球最大的同性交友网站lol）拿出来装个逼:免费，快速，搞的定！，，，于是就开始写这篇博文~~~


##准备


首先，你需要准备好以下几个东西：

1. 属于你自己的Github账号[https://github.com/](https://github.com/)
2. 了解Github的基础使用方法，并创建一个仓库（repository）,不会的话请用搜索引擎~
3. 适宜的工作环境，舒展以下筋骨，然后还可以带上耳机听点Rock & Roll~


##步骤

1. 打开命令行，将你创建好的仓库克隆到本地： `git clone github.com/user/repository.git`
2. 进入你的仓库：`cd repository`
3. 创建独立并切换到gh-pages分支：`git checkout --orphan gh-pages`
4. 如果是你已经存在的仓库，移除现有仓库gh-pages分支的所有内容：`git rm -rf .`
5. 创建你的网页文件，并提交到gh-pages分支（要有个index.html文件，提交代码如下）


		echo "My Page" > index.html

		git add index.html

		git commit -a -m "First pages commit"

		git push origin gh-pages



##完工

好了，打开你的浏览器，在地址栏输入`http(s)://<username>.github.io/<projectname>`，然后按下键盘上的回车，看看是不是得到了你的网页效果啦~~~


##真相

哎，其实会用Github的话，其实就一个简单，看看下面的链接就搞定了~

[Github官方说明指南](https://help.github.com/articles/creating-project-pages-manually/)

