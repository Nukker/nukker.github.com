---
layout: post
title:  搭建Jekyll问题总结
date:   2014-01-16 16:59
category: "Jekyll"
---

 本以为是个简单的部署就能使用,谁想到各种曲折一弄弄了两天才部署好。
这里把出现的问题做个记录，以备以后再次误入歧途。

部署环境:Windows 7-64位

##Jekyll总体部署流程

h3. Step1

Jekyll是使用ruby写的静态网页生成工具,要本地能预览就要先配置好Ruby

h3. Step2

装Rubyinstaller-1.9.3-p484吧,稳定健壮些,之前装了Ruby2.0出来一堆BUG束手无策，安装时把选项都勾上可以帮你添加好系统环境变量

h3. Step3

对应还要安装一个叫DevKit-tdm-32-4.5.2-20110712-1620-sfx.exe在Windows平台下模拟编译C/C++的拓展包
解压好Dev后,CMD进入到解压目录,依次输入以下命令
	
{% highlight bash %}
$ ruby dk.rb init     #初始化生成一个config.yml文件写入ruby的安装目录
$ ruby dk.rb install   #安装
{% endhighlight %}

h3. Step4

利用gem命令安装jekyll
	
{% highlight bash %}
$ gem install jekyll  #目前默认安装的是1.4.3,这个版本目前对WINDOWS的目录处理有一个BUG,还是安装上一个版本才能生效
$ gem install jekyll --version "=1.4.2"
{% endhighlight %}

h3. Step5

CD到你仓库目录下,进行本地加载
	
{% highlight bash %}
$ jekyll serve
{% endhighlight %}

这时就可以访问:http://localhost:4000/ or http://0.0.0.0:4000/



