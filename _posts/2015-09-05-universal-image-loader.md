---
layout: post
title: Universal-Image-Loader图片框架使用入门
excerpt: "Android开发资源导航神器"
date: 2015-09-05 11:13:56
categories: Android

---

* content
{:toc}

 
  

###需求
 
在安卓开发过程中和图片打交道的时候难免会遇到以下几个情况：

1. 图片异步加载
2. 图片缓存
3. 图片显示
4. 图片OOM（内存溢出问题）
5. 其它……（忘记了）

以上的这些情况，可能要自己去写不少代码去实现这些功能，而且对于一些新手，可能写了半天，发现效果很不理想、内存问题也处理不好、异步也不好控制（我就是这样）。所以搜了一下，发现网上最流行的一个安卓图片开源框架 [universal-image-loader](https://github.com/nostra13/Android-Universal-Image-Loader)，亲自使用了一下，发现真是的好用啊！一共就加十几行代码就搞定了，妈妈再也不用担心我花时间去瞎搞八搞的了！

###使用

好了，下面来说说快速使用这个框架的步骤：

1. 往工程的libs文件夹中添加 universal-image-loader-1.9.2-with-sources.jar 这个Jar包。点击这里可以直接下载哦！

2. 新建一个 继承application的类，其中的代码看下面：

...

	public class MyApplication extends Application {  
	public void onCreate() {  
	    super.onCreate();  
	    initImageLoader(getApplicationContext());  
	}  
	
	public static void initImageLoader(Context context) {  
        ImageLoaderConfiguration config = new 	ImageLoaderConfiguration.Builder(context)  
                .threadPriority(Thread.MAX_PRIORITY).deny	CacheImageMultipleSizesInMemory()  
                .diskCacheFileNameGenerator(new 		Md5FileNameGenerator()).tasksProcessingOrder(QueueProcess	ingType.LIFO)  
                .writeDebugLogs() // Remove for release 	app  
	                .build();  
	        ImageLoader.getInstance().init(config);  
	    }  
  
	}  


注意，这个application类要在menifest中的application标签中注明哦！就是下面这样：

	<application
        android:name="com.lee.example.MyApplication"


好了，添加完以上两步的内容，基本的框架环境就搭建好了，下面是如何使用它来加载网络图片：
先声明两个对象：

	private DisplayImageOptions options;
	private ImageLoader imageLoader;

然后在类的构造函数或者activity的increate方法中初始化它们：

	imageLoader = ImageLoader.getInstance();
	options = new DisplayImageOptions.Builder()
	.showImageOnLoading(null)//加载过程中显示的图片
	.showImageForEmptyUri(null)//加载内容为空显示的图片
	.showImageOnFail(null)//加载失败显示的图片
	.cacheInMemory(true).cacheOnDisk(true).considerExifParams(true)
	.bitmapConfig(Bitmap.Config.RGB_565).displayer(new FadeInBitmapDisplayer(388)).build();
	
下面是使用：

	imageLoader.displayImage(imageFile, imageView, options);

说明：
imageFile：图片的网络路径（也可以用本地的路径哦，详情看文末的框架github中的文档说明）

imageView：就是图片控件哈~

就上面这么一句，太方便了哈！


###源码

框架的github地址：[https://github.com/nostra13/Android-Universal-Image-Loader](https://github.com/nostra13/Android-Universal-Image-Loader)
