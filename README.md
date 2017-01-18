# 优秀的android图片加载框架Universal-image-loader
开源项目地址:[https://github.com/open-android/Universal-Image-Loader](https://github.com/open-android/Universal-Image-Loader)
# 运行效果
  ![](https://github.com/nostra13/Android-Universal-Image-Loader/raw/master/UniversalImageLoader.png)
  
  * 爱生活,爱学习,更爱做代码的搬运工,分类查找更方便请下载黑马助手app


![黑马助手.png](http://upload-images.jianshu.io/upload_images/4037105-f777f1214328dcc4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 使用步骤
### 1. 在project的build.gradle添加如下代码(如下图)

	allprojects {
	    repositories {
	        ...
	        maven { url "https://jitpack.io" }
	    }
	}
  
### 2. 在Module的build.gradle添加依赖

    compile 'com.github.open-android:Universal-Image-Loader:0.1.0'
### 3. 复制如下代码到application中 初始化ImageLoader

	   ImageLoader.getInstance().init(ImageLoaderConfiguration.createDefault(this));

	   //如果想更加详细的初始化请使用下面的初始化方法：
	   ImageLoaderConfiguration.Builder config = new ImageLoaderConfiguration.Builder(context);
			config.threadPriority(5);//设置加载图片的线程个数
			config.diskCacheSize(50 * 1024 * 1024); // 设置本地缓存的大小
			ImageLoader.getInstance().init(config.build());
### 4. 复制如下代码到Activity中

	  ImageLoader.getInstance().displayImage(url,imageView);
	  //如果想设置一些详细的图片加载信息，请使用下面重载的方法：
	  DisplayImageOptions options = new DisplayImageOptions.Builder()
						.showImageOnLoading(R.drawable.ic_stub) //设置图片加载时显示的图片
						.showImageForEmptyUri(R.drawable.ic_empty) //设置图片加载地址为空时显示的图片
						.showImageOnFail(R.drawable.ic_error) //设置图片加载错误时显示的图片
						.cacheInMemory(true) //设置可以在内存中缓存
						.cacheOnDisk(true) //可以在本地缓存
						.displayer(new CircleBitmapDisplayer(Color.WHITE, 5)) //设置展示图片为圆角
						.build();
	  ImageLoader.getInstance().displayImage(IMAGE_URLS[position], holder.image, options);
	  
### 5. 在AndroidManifest.xml中配置网络权限

    <uses-permission android:name="android.permission.INTERNET" />
    
    
* 详细的使用方法在DEMO里面都演示啦,如果你觉得这个库还不错,请赏我一颗star吧~~~

* 欢迎关注微信公众号

![](http://upload-images.jianshu.io/upload_images/4037105-8f737b5104dd0b5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)   
  
  
