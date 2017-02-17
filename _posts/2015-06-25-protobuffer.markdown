---
layout: post
keywords: blog
description: blog
title: "Protobuffer学习"
categories: [android]
tags: [google]
group: android

---
{% include codepiano/setup %}

## 什么是Protocol Buffers(简称PB)?

&nbsp;&nbsp;&nbsp;&nbsp;[谷歌官方文档](https://developers.google.com/protocol-buffers/)上解释Protocol buffers是一种灵活、高效、自动序列化结构数据的机制-类似XML,但比XML更小，更快，更简单。你可以自己定义你所需要的结构化数据,然后使用特殊生成的代码简单的读取或者写入结构化数据到一系列数据流,而且它支持好几种语言。你可以更新你的结构化数据格式而不会与部署的旧的格式冲突。<br>
&nbsp;&nbsp;&nbsp;&nbsp;总结以上Protocol Buffers 是一种轻便高效的结构化数据存储格式，可以用于结构化数据串行化，或者说序列化。它很适合做数据存储或 RPC 数据交换格式。可用于通讯协议、数据存储等领域的语言无关、平台无关、可扩展的序列化结构数据格式。目前提供了 C++、Java、Python 三种语言的 API。
   
## Protocol Buffers如何工作？

### 1.定义.proto文件<br>
&nbsp;&nbsp;&nbsp;&nbsp;根据需要在.proto文件中定义需要的结构化数据。

*  .proto文件中可以选择性的定义一个package,用于在不同消息类型中引用。
* 这里可以定义java_package指明生成类所在的包,
java_outer_classname指明生成的类名。
* message对应各种可读写的pb信息,message可以嵌套。
* message中可以定义double,float,int32,int64,uint32,uint64,bool,
string,bytes
等数据类型。
* 每种数据类型前面有可以添加required(必须)、optional(可选)、repeated(可重复)标识。<br>

 {% highlight java %}
 package tutorial;

option java_package = "com.example.tutorial";
option java_outer_classname = "AddressBookProtos";

message Person {
  required string name = 1;
  required int32 id = 2;
  optional string email = 3;

  enum PhoneType {
    MOBILE = 0;
    HOME = 1;
    WORK = 2;
  }

  message PhoneNumber {
    required string number = 1;
    optional PhoneType type = 2 [default = HOME];
  }

  repeated PhoneNumber phone = 4;
}

message AddressBook {
  repeated Person person = 1;
}
{% endhighlight %}
  
### 2.运行protocol buffer编译器生成序列化存储和解析类

* 提供get和set方法以及write和parse方法来生成、序列化、解析pb messages。你可以序列化存储到文件等地方,然后也可以从输入流中解析这些pb信息,而且PB支持扩展,你可以动态修改.proto文件重新生成新的序列化类,而不用担心兼容老版本格式。
* 可以将.proto文件置于工程src下，然后执行命令protoc ./**.proto  - -java_out=./即可生成proto序列化解析类(注:- -之间无空格)

### 3.使用生成的Protocol Buffer API
  {% highlight java %}
Person john = Person.newBuilder()
    .setId(1234)
    .setName("John Doe")
    .setEmail("jdoe@example.com")
    .addPhone(
      Person.PhoneNumber.newBuilder()
        .setNumber("555-4321")
        .setType(Person.PhoneType.HOME))
    .build();
  {% endhighlight %}

## 为什么不使用XML等格式？
&nbsp;&nbsp;&nbsp;&nbsp;protocol buffers相比XML有很多优点：更简单，更小，更快,很方便使用生成的解析类。

## 安全性
&nbsp;&nbsp;&nbsp;&nbsp;protocol buffers序列化存储后是二进制的信息,除非有.proto文件不然无法解析信息,这点比Json,XML等格式更安全。当然你也可以进一步对pb信息进行加密和解密。

### 参考：<br>
[Protocol Buffer官方文档](https://developers.google.com/protocol-buffers/)<br>
[Google Protocol Buffer 的使用和原理](http://www.ibm.com/developerworks/cn/linux/l-cn-gpb/)
