---
layout: post
keywords: blog
description: blog
title: "protobuffer学习"
categories: [android]
tags: [google]
group: android

---
{% include codepiano/setup %}

##什么是Protocol Buffers?

   [谷歌官方文档](https://developers.google.com/protocol-buffers/)上解释Protocol buffers是一种灵活、高效、自动序列化结构数据的机制-类似XML,但比XML更小，更快，更简单。你可以自己定义你所需要的结构化数据,然后使用特殊生成的代码简单的读取或者写入结构化数据到一系列数据流,而且它支持好几种语言。你可以更新你的结构化数据格式而不会与部署的旧的格式冲突。<br>
   总结以上Protocol Buffers 是一种轻便高效的结构化数据存储格式，可以用于结构化数据串行化，或者说序列化。它很适合做数据存储或 RPC 数据交换格式。可用于通讯协议、数据存储等领域的语言无关、平台无关、可扩展的序列化结构数据格式。目前提供了 C++、Java、Python 三种语言的 API。


###参考：<br>
[Protocol Buffer官方文档](https://developers.google.com/protocol-buffers/)