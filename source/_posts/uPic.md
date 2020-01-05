---
title: 图片/文件上传如此简单｜macOS 图床客户端-uPic
tags:
  - CSS
  - Web
categories: Essays
date: 2020/01/05
thumbnail: https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic/banner.png
toc: true
widgets:
  - type: toc
    position: left
  - type: recent_posts
    position: right
sidebar:
  left:
    sticky: true
  right:
    sticky: true
---


## 前言

相信很多人在写作（特别是需要多平台发布）的时候都会因为插图而增加工作量：
* 平台图片外链不允许在网站外部访问。
* 使用云图床服务上传流程复杂。

那么这些问题有没有办法解决呢，答案肯定是“有”。
* Swift 原生开发的 macOS 端 iPic。
* Electron 开发的跨平台 PicGo。
* …

这些软件都可以很好的解决这些问题，那为什么我还会再开发一款此类APP呢？原因有以下几点：
1. PicGo 每个类型的图床只能有一个配置，我个人有习惯将不同的用途的图片用多个图床区分。
2. 个人比较喜欢用快捷键来完成这一系列操作。（最新版 PicGo 好像也已经支持了快捷键）
3. PicGo 和 iPic 的路径规则支持都不多。

**最重要的一点是我从 Windows 电脑换成 MacBook Pro 作为主力开发机后，就一直想学一学 Swift 开发。于是这就成为了我开发 uPic 的契机！**

<!--more-->

## uPic 介绍
uPic 采用 Swift 原生开发，通过调用各个服务商的 API 接口实现。体积小、速度快。支持多种图床：[smms](https://sm.ms/), [又拍云 USS](https://www.upyun.com/products/file-storage), [七牛云 KODO](https://www.qiniu.com/products/kodo), [阿里云 OSS](https://www.aliyun.com/product/oss/), [腾讯云 COS](https://cloud.tencent.com/product/cos), [百度云 BOS](https://cloud.baidu.com/product/bos.html), [微博](https://weibo.com/), [Github](https://github.com/settings/tokens), [码云 Gitee](https://gitee.com/profile/personal_access_tokens), [Amazon S3](https://aws.amazon.com/cn/s3/), [Imgur](https://imgur.com/), [自定义上传服务](https://blog.svend.cc/upic/tutorials/custom), ...

![支持图床](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/hosts.png)

uPic 还支持多种常用的输出格式，并且提供上传前图片压缩功能(支持 JPG、PNG)。等等一些小功能…

![菜单栏](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/menu.png)


### 多种上传方式
> 在上传方面支持了更多重方式以应对不同的使用场景：除了`选择文件`，`拖拽文件到菜单栏`这些最基本的上传操作外。uPic 还支持`从剪切板获取文件上传`、`截图上传`、`从浏览器直接拖拽文件上传`、`Finder 右键上传`以及`命令行上传`。

*  选择文件上传`支持自定义全局快捷键`
![选择文件上传](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/selectFile-shortcut.gif)

* 从剪切板获取文件上传`支持自定义全局快捷键`
![从剪切板获取文件上传](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/pasteboard-shortcut.gif)

* 截图上传`支持自定义全局快捷键`
![截图上传](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/screenshot-shortcut.gif)

* 拖拽本地文件上传
![拖拽本地文件上传](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/dragFile.gif)

* 拖拽浏览器文件上传
![拖拽浏览器文件上传](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/dragFromBrowser.gif)

* Finder 右键菜单上传
![Finder 右键菜单上传](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/contextmenu.gif)

* 命令行上传
![命令行上传](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/cli.gif)

### 强大的图床配置
> 在图床配置方面简单又灵活。  
> 特别是在保存路径配置上 uPic 提供了极其灵活的配置方案，可根据自己的使用习惯或需求来随意搭配。  

![图床配置](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/host-preferences.png)

如图：最终保存在服务上的路径会是`2020/1/5/filename.png`

### 精美的上传历史
> 上传历史采用瀑布流方式展示最近上传的文件缩略图，鼠标悬浮展示原图。  
> 方便查找。  

![上传历史](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/history.png)

并且历史界面的展示效果可以自行配置。
![上传历史](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/shortcuts.png)


## 结束语
目前 uPic 已在 [Gtihub](https://github.com/gee1k/uPic) 开源，👏 欢迎大家下载尝试。 🤓 期待您的建议与反馈！
可在 [微博](https://weibo.com/gee1k)、[Twitter](https://twitter.com/geee1k)或[TG](https://t.me/gee1k)上联系我。
更多信息和联系方式可在 [Github](https://github.com/gee1k/uPic) 上查看。