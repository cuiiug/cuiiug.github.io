---
layout: post
title:  "从WordPress到静态网站"
date:   2017-08-01 12:00:00
categories: coding4fun
tags: [github, jekyll, bootstrap]
---

作为一个极简主义者，越来越受不了WordPress的臃肿。主要自己平时都是用Markdown来做记录，而WordPress支持的不是很好，另外有时写的md长文通过三方软件导出的html也不造放在wp的什么地方才合适，管理起来还不如几个静态页面来得方便。于是有了某天来个大整顿的想法。

对前端只停留在css的我，花了整三天时间，从Hexo到Jekyll再到Bootstrap，以及各种markdown2html解析器...最后基本算是从头写了一个基于Jekyll的website theme 😓  在此记录了各种前端坑，自认为还算详细吧。<!-- more -->


# Hexo

主流的静态页面生成器有俩，一个Jekyll，一个Hexo，都支持Markdown。 前者用的是Ruby，后者为Node.js。

Hexo会比Jekyll搭建起来更方便一些，而且各种配置项的设计也很便捷，网站themes还很丰富，所以我一开始弄的就是这个。

* [Hexo官方文档](https://hexo.io/zh-cn/docs/)
* [next](https://github.com/iissnan/hexo-theme-next) : 一款优雅并且功能强大的主题. [[doc]](http://theme-next.iissnan.com/getting-started.html) [[demo]]([http://notes.iissnan.com](http://notes.iissnan.com/))

搭建方法上面这两个链接写的很详细。

这里主要记录一下让Hexo支持LaTex的注意地方。Hexo用MathJax时会有一些[转义问题](http://2wildkids.com/2016/10/06/%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86Hexo%E5%92%8CMathJax%E7%9A%84%E5%85%BC%E5%AE%B9%E9%97%AE%E9%A2%98/#)，经我自己测试，最好的方式是用`hexo-renderer-pandoc`渲染器代替原有的`hexo-renderer-marked`。而网上说的用`hexo-renderer-kramed`，对矩阵的情况显示的不好。

~~~
$ npm uninstall hexo-renderer-marked --save
$ npm install hexo-renderer-kramed --save
~~~



