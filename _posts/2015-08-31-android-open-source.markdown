---
layout: post
keywords: blog
description: blog
title: "Android开源框架分析"
categories: [android开源框架]
tags: [android]
group: android

---
{% include codepiano/setup %}

## 常用Android开源框架

### 1.Volley
&nbsp;&nbsp;&nbsp;&nbsp;Volley 是 Google 在 2013 I/O 大会上推出的 Android 异步网络请求框架和图片加载框架。特别适合数据量小，通信频繁的网络操作。Volley 主要是通过两种 Diapatch Thread 不断从 RequestQueue 中取出请求，根据是否已缓存调用 Cache 或 Network 这两类数据获取接口之一，从内存缓存或是服务器取得请求的数据，然后交由 ResponseDelivery 去做结果分发及回调处理。

* 项目地址: 
[Volley](https://android.googlesource.com/platform/frameworks/volley/)
* 源码分析:
[CodeKK](http://codekk.com/open-source-project-analysis/detail/Android/grumoon/Volley%20%E6%BA%90%E7%A0%81%E8%A7%A3%E6%9E%90)

### 2.EventBus
&nbsp;&nbsp;&nbsp;&nbsp;EventBus 是一个 Android 事件发布/订阅框架，通过解耦发布者和订阅者简化 Android 事件传递，这里的事件可以理解为消息，本文中统一称为事件。事件传递既可用于 Android 四大组件间通讯，也可以用户异步线程和主线程间通讯等等。传统的事件传递方式包括：Handler、BroadCastReceiver、Interface 回调，相比之下 EventBus 的优点是代码简洁，使用简单，并将事件发布和订阅充分解耦。

* 项目地址:
[EventBus](https://github.com/greenrobot/EventBus)
* 源码分析:
[CodeKK](http://codekk.com/open-source-project-analysis/detail/Android/Trinea/EventBus%20%E6%BA%90%E7%A0%81%E8%A7%A3%E6%9E%90)

### 3.Android Universal Image Loader
&nbsp;&nbsp;&nbsp;&nbsp;Universal Image Loader 是一个强大的、可高度定制的图片缓存。整个库分为 ImageLoaderEngine，Cache及ImageDownloader，ImageDecoder，BitmapDisplayer，BitmapProcessor 五大模块，其中 Cache 分为 MemoryCache 和 DiskCache 两部分。简单的讲就是 ImageLoader 收到加载及显示图片的任务，并将它交给 ImageLoaderEngine，ImageLoaderEngine 分发任务到具体线程池去执行，任务通过 Cache 及 ImageDownloader 获取图片，中间可能经过 BitmapProcessor 和 ImageDecoder 处理，最终转换为 Bitmap 交给 BitmapDisplayer 在 ImageAware 中显示。

* 项目地址:
[UIL](https://github.com/nostra13/Android-Universal-Image-Loader)
* 源码分析:
[CodeKK](http://codekk.com/open-source-project-analysis/detail/Android/huxian99/Android%20Universal%20Imge%20Loader%20%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90)

### 5.NineOldAndroids
&nbsp;&nbsp;&nbsp;&nbsp;NineOldAndroids 是一款支持在低版本(API 11 以下)使用 Android 属性动画以及 3D 旋转动画的框架，它提供了一系列如 ViewAnimator, ObjectAnimator, ViewPropertyAnimator 等 API 来完成这些动画，解决了 Android 动画框架在低版本的兼容性问题。在 API 11 (Honeycomb-Android 3.0)后 Android 推出了属性动画、X 轴翻转等动画效果，但是这些效果却不能运行在 API 11 以下，NineOldAndroids 的出现使得这些动画效果能够兼容低版本系统，保证动画在各个系统版本能够完美运行。

* 项目地址:
[NineOldAndroids](https://github.com/JakeWharton/NineOldAndroids)
* 源码分析:
[CodeKK](http://codekk.com/open-source-project-analysis/detail/Android/Mr.Simple/NineOldAnimations%20%E6%BA%90%E7%A0%81%E8%A7%A3%E6%9E%90)

### 6.Picasso
&nbsp;&nbsp;&nbsp;&nbsp;一个强大的图片下载和缓存库。

* 项目地址:
[Picasso](https://github.com/square/picasso)

### 7.ButterKnife
&nbsp;&nbsp;&nbsp;&nbsp;利用annotation帮你快速完成View的初始化,了解annotation的原理可以查看[CodeKK Annotation](http://codekk.com/open-source-project-analysis/detail/Android/Trinea/公共技术点之%20Java%20注解%20Annotation)

* 项目地址：[ButterKnife](https://github.com/JakeWharton/butterknife)
* 文档介绍：[使用文档说明](http://jakewharton.github.io/butterknife/
)


