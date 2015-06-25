---
layout: post
keywords: blog
description: blog
title: "Jekyll学习"
categories: [Jekyll]
tags: [Jekyll]
---
{% include codepiano/setup %}

#Learn Jekyll
  
&nbsp;&nbsp;&nbsp;&nbsp;偶然在网上看到[StormZhang](http://stormzhang.com)的博客,觉得很不错,简单清晰,萌发也做一个一样的技术博客,查看他是使用Octopress做的博客,然后后来改成Jekyll。
  
##Jekyll简介

&nbsp;&nbsp;&nbsp;&nbsp;Jekyll 的核心其实是一个文本转换引擎。它的概念其实就是：你用你最喜欢的标记语言来写文章，可以是 Markdown，也可以是 Textile,或者就是简单的 HTML, 然后 Jekyll 就会帮你套入一个或一系列的布局中。在整个过程中你可以设置URL路径, 你的文本在布局中的显示样式等等。这些都可以通过纯文本编辑来实现，最终生成的静态页面就是你的成品了。


##Jekyll安装

* Ruby
* RubyGems
* Git
* Jekyll

##Jekyll自动化

&nbsp;&nbsp;&nbsp;&nbsp;首先到这[jekyll-bootstrap](https://github.com/plusjade/jekyll-bootstrap/blob/master/Rakefile) 去下这个rakefile,通过rakefile可以自动生成post并且加入yaml头部.把这个文件放入jekyll的根目录.rakefile文件中可以修改post_ext生成的文件格式为md或者html等。在jekyll目录里执行rake post title ="test",会在_posts目录自动生成含yaml头的yyyy-mm-dd-test.md的post文件,执行open yyyy-mm-dd-test.md打开文件修改后即可发布。

{% highlight ruby %}

CONFIG = {
  'version' => "0.3.0",
  'themes' => File.join(SOURCE, "_includes", "themes"),
  'layouts' => File.join(SOURCE, "_layouts"),
  'posts' => File.join(SOURCE, "_posts"),
  'post_ext' => "md",
  'theme_package_version' => "0.1.0"
}

{% endhighlight %}



参考:  <br>[Jekyll](http://jekyll.bootcss.com)<br>
       [搭建一个免费的Github Pages博客](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)



 