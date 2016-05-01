---
layout: post
title: 自定义双列线性布局
excerpt: "自定义双列线性布局，代替gridview的简单方法"
date: 2015-11-09 12:25:55
categories: Android

---


因为公司项目里面有个listview里面的item里面需要一个双列列表，想着如果嵌套一个gridview的话，感觉会很糟糕，所以干脆自定义一个ViewGroup去实现双列的线性布局，然后把内容一个个addview添加进去就好了。。。

下面是这个自定义view的代码，其实很简单~~~

<script src="https://gist.github.com/ColorfulCat/8ac7b947f349a0a49a28.js"></script>

这还是生平第一次使用gist功能，好害羞~~~~⁄(⁄ ⁄•⁄ω⁄•⁄ ⁄)⁄