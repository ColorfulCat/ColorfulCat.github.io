---
layout: post
title: Android中禁用多点触控的方法
excerpt: "Android中禁用多点触控的方法，解决同时按下多个按钮所造成的一些问题"
date: 2015-10-20 10:11:06
categories: Android

---

* content
{:toc}


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
在安卓开发过程中，偶尔会遇到一些情况：同时按下多个按钮，触发多个事件，引起事件冲突。例如：同时按下两个会引发dialog的按钮，就会弹出两个dialog。这是问题，当然要解决，一下是两个解决这个问题的简单方法：

###方法一

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
使用自定义主题Theme来修改整个APP的主题样式，禁止全局多点触控：

	<style name="MyThemeStyle"> <!-- 禁止多点触控 -->
    	<item name="android:windowEnableSplitTouch">false</item>
    	<item name="android:splitMotionEvents">false</item>
	</style>


###方法二

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
在需要禁用多点触控的地方，给按钮的Parent Layout添加禁用多点触控的属性：

	android:splitMotionEvents="false" 


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
注意：以上方法需要在API11（Android 3.0）以上才能使用哦~

###官方文档解释

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
有兴趣详细研究的，可以去官方文档好好阅读一下~ [《点此进入》](http://developer.android.com/reference/android/R.attr.html#splitMotionEvents)

