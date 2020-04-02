---
title: 简洁的 Mac 图床客户端 uPic
date: 2019-06-24 20:42:43
thumbnail: //s2.svend.cc/thumb/done.svg
toc: true
widgets:
  - type: toc
    position: right
sidebar:
  left:
    sticky: true
  right:
    sticky: true
---
<div align="right">**🇨🇳中文** | [**🇬🇧English**](./en)</div>

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic/logo.png" alt="uPic">
</div>

# ☁️ 简洁的 Mac 图床客户端 uPic

<div style="display: flex;justify-content: center;" align="center">
	<a href="https://github.com/gee1k/uPic/releases/latest">
    <img src="https://img.shields.io/github/release/gee1k/uPic?label=version&style=flat-square" alt="">
  </a>
	<a href="https://github.com/gee1k/uPic/releases" style="margin: 0 5px;">
    <img src="https://img.shields.io/github/downloads/gee1k/uPic/total.svg?style=flat-square" alt="">
  </a> 
  <a href="https://github.com/gee1k/uPic/blob/master/LICENSE">
		<img alt="GitHub" src="https://img.shields.io/github/license/gee1k/uPic?style=flat-square">
	</a>
</div>


## 📑 简介

> **uPic(upload Picture) 是一款 Mac 端的图床(文件)上传客户端**
> 可将图片、各种文件上传到配置好的指定提供商的对象存储中。
> 然后快速获取可供互联网访问的文件 URL

**💡 特点：** 无论是本地文件、或者屏幕截图都可自动上传，菜单栏显示实时上传进度。上传完成后文件链接自动复制到剪切板，让你无论是在写博客、灌水聊天都能快速插入图片。
连接格式可以是普通 URL、HTML 或者 Markdown，仍由你掌控。

**🔋 支持图床：** [smms](https://sm.ms/)、 [又拍云 USS](https://www.upyun.com/products/file-storage)、[七牛云 KODO](https://www.qiniu.com/products/kodo)、 [阿里云 OSS](https://www.aliyun.com/product/oss/)、 [腾讯云 COS](https://cloud.tencent.com/product/cos)、[微博](https://weibo.com/)、[Github](https://github.com/settings/tokens)、 [Gitee](https://gitee.com/profile/personal_access_tokens)、 [Amazon S3](https://aws.amazon.com/cn/s3/)、[自定义上传接口](https://blog.svend.cc/upic/tutorials/custom)、...

## 🚀 如何安装

### 下载安装
#### 1.Homebrew:
```
brew cask install upic
```
#### 2.手动
从 [Github release](https://github.com/gee1k/uPic/releases) 下载。
**如果访问 Github 下载困难的，可以从[Gitee release](https://gitee.com/gee1k/uPic/releases)下载。**

### 检查 Finder 扩展权限

- 1.打开 uPic

- 2.打开`系统偏好设置` - `扩展` - `访达扩展` 确保 `uPicFinderExtension`是勾选状态

  <center>
    <img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/finder-extension.png" height="300">
  </center>



## 🕹 使用方式

| 功能 | 描述 | 预览 |
| --- | --- | --- |
| **🖥 选择文件上传** | 从`Finder`选择文件上传。`可设置全局快捷键` | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/selectFile.gif) |
| **⌨️ 复制文件上传** | 上传已拷贝到剪切板的文件。`可设置全局快捷键` | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/pasteboard.gif) |
| **📸 截图上传** | 直接拉框截图上传。`可设置全局快捷键` | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/screenshot.gif) |
| **🖱 拖拽本地文件上传** | 拖拽文件到状态栏上传 | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/dragFile.gif) |
| **🖱 拖拽浏览器图片上传** | 从浏览器拖拽图片到状态栏上传 | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/dragFromBrowser.gif) |
| **📂 Finder 中右键上传** | 右击文件上传 | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/contextmenu.gif) |
| **⌨️ 命令行上传** | 通过执行命令调用 uPic 上传文件 | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/cli.gif) |



## 🧰 更多功能

### 1.全局快捷键
<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/shortcuts.png" height="300">

### 2. 上传历史
<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-cn/history.png" height="300">

## 📝 使用手册

- [uPic 图床配置教程 - 微博](./tutorials/weibo)
- [uPic 图床配置教程 - 又拍云](./tutorials/upyun_uss)
- [uPic 图床配置教程 - 七牛云](./tutorials/qiniu_kodo)
- [uPic 图床配置教程 - 阿里云](./tutorials/aliyun_oss)
- [uPic 图床配置教程 - 腾讯云](./tutorials/tencent_cos)
- [uPic 图床配置教程 - 百度云](./tutorials/baidu_bos)
- [uPic 图床配置教程 - Amazon S3](./tutorials/amazon_s3)
- [uPic 图床配置教程 - Github](./tutorials/github)
- [uPic 图床配置教程 - 码云(Gitee)](./tutorials/gitee)
- [uPic 图床配置教程 - Imgur](./tutorials/imgur)
- [uPic 图床配置教程 - 自定义上传](./tutorials/custom)
- [uPic 图床配置教程 - Chevereto](./tutorials/chevereto)

## 💌 联系我

- `Email`: svend.jin@gmail.com
- `Telegram`: [gee1k](https://t.me/gee1k)
- `项目地址`: [Github](https://github.com/gee1k/uPic)
- `uPic 产品交流群(Telegram)`:  [点击加入 TG 群](https://t.me/upic_host)
- `微信群`:  <small>扫描下方二维码加好友拉你入群 ↓ </small>

	<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/personal/geee1k.JPG" height="200">

## 🤙 特别感谢

### 翻译
- [@m01i0ng](https://github.com/m01i0ng)
- [@Jackxun123](https://github.com/Jackxun123)
- [@kkkkkkyrie](https://github.com/kkkkkkyrie)
