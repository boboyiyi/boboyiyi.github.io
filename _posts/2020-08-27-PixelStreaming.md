---
layout: post
title: UE4实现Pixel Streaming
date: 2020-08-27
tags: UE4
---

![](/images/posts/UE4/PixelStreaming.jpg)

### 概述

项目需要把UE4的渲染结果通过类似Pixel Streaming的方式输出从而实现云端渲染，
云端渲染的好处是大大降低了设备端的显卡需求，只要网速和播放视频的要求可以满足，
就能得到与云端渲染完全一致的效果。

云端渲染的拓展词条：云游戏（Cloud Gaming），云OS（比如AliOS）

我能想到两种方案：
1. GPU -> CPU -> gRPC -> Encoder -> Streaming
2. GPU -> GPU Encoder -> gPRC -> Encoder -> Streaming



### 概念

#### BackBuffer
Front buffer = what is being shown on screen (the last frame)

Back buffer = where you're currently drawing (the current frame)


#### RHI
UE4中的RHI指的是Render Hardware Interface

两种解决方案：

### 方案1
GPU上的BackBuffer获取的一个TArray<FColor> Data;


### 方案2

- [x] 适配电脑、手机、平板等各屏幕
- [x] 响应式设计
- [x] 个性化头像
- [x] 每篇文章自动添加打赏功能
- [x] 支持Disqus、livere评论系统
- [x] 支持站点总数访问统计，每篇文章访问统计
- [x] 支持文章自动生成目录
- [x] 支持标签分类
- [x] 支持代码高亮
- [x] 支持文章H1、H2、H3、H4标题样式多样化
- [x] 支持多种三方社交icon展示，能从博客直接跳转到自己的三方社交主页
- [x] 支持三方社交分享(facebook、twitter)


## 博客主要模块介绍

### _config.yml 

`_config.yml` 是博客的配置文件，整个站点的信息都在这修改，想要把我的模板改成你自己的也需要修改`_config.yml` 

**重要字段说明** 

* enableToc: 是否开启文章自动生成目录，设置为false文章不会自动生成目录
* comment/livere: livere评论系统，支持微信、qq、微博、豆瓣、twitter等登录后可以直接评论
* comment/disqus: disqus评论系统，支持facebook、twitter等登录后可以直接评论
* social/weibo、github、zhihu、jianshu等: 个人站底部展示的微博等三方社交按钮，点击后直接跳转到个人微博或其他社交主页
* baidu/id: 百度统计，用来统计你个人站点的用户访问情况
* ga/id: google统计，用来统计你个人站点的用户访问情况

_config.yml 文件除以上字段还有一些可以自行修改，例如title之类的字段

### _posts

`_posts` 目录是用来存放文章的目录，写新文章，直接放在这个目录即可

使用博客模板时，请把博客自带的文章给去掉，如果想使用博客自带的文章请 `注明出处`。


### 自定义页面

about.md、support.md 等为自定义页面，如果你想添加自动以页面可以直接复制about.md 文件修改文件名和里面的内容即可。

如果需要在导航显示你新增的页面，直接在`_config.yml` 文件的nav字段中添加你新页面配置即可

### 修改说明

如果要修改博客模板信息建议只修改`_config.yml` 文件内容和 `_posts` 里面的文章信息。因为博客模板一直在更新迭代，改动多了以免你后期更新博客模板的时候不方便。

如果你想改动模板的样式又想继续更新迭代博客模板，你可以提交在github上提交`pull request` 或者直接给我发邮件建议改成什么样，如果你的提议确实可以，我会采纳的，并且非常感谢你的建议。

博客迭代信息请看[ReleaseNode](https://leopardpan.cn/2020/07/ReleaseNode/)

遇到解决不了的问题可以找 [技术支持](https://leopardpan.cn/support/)





