---
layout: post
keywords: blog
description: blog
title: "Android adb"
categories: [Android]
tags: [Android小知识]
group: Android

---
{% include codepiano/setup %}

##一.利用run-as命令在不root的情况下读取data下面数据

转载: [农民伯伯](http://www.cnblogs.com/over140/archive/2012/06/13/2547706.html)

###1.关键步骤
adb shell下面运行run-as命令

{% highlight c %}
 	$ adb shell
	$ run-as com.package
	$ cd /data/data/com.package
	$ ls
	databases
	lib
	$ cd databases
	$ ls
	preferences.db
	$ cat preferences.db > /mnt/sdcard/preferences1.db 
	$ cp -r lib /mnt/sdcard/
{% endhighlight %}  

代码说明：

注意com.package换成自己的完整包名，关键是run-as命令，最后使用cat命令把文件拷贝到其它位置,或者使用cp -r 命令拷贝文件。

###2.补充
&nbsp;&nbsp;&nbsp;&nbsp;/data/data/package/lib这个目录是可以直接访问的，也就是说adb shell后虽然无法读取/data目录，但是可以直接访问这个目录下的文件，可以通过上面的run-as命令看得出其权限与其他目录的权限是不同的，为system权限，这为多apk共享so提供了便利，这也是Vitamio所使用的方式。

如果签名了并且指定设置了android:debuggable="false"将无法使用该命令。

###参考
[denied-to-data use adb](http://stackoverflow.com/questions/1043322/why-do-i-get-access-denied-to-data-folder-when-using-adb)

