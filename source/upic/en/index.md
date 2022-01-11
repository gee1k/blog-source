---
title: Terse image hosting client uPic for Mac
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

<div align="right">[**🇨🇳中文**](../) | **🇬🇧English**</div><!-- i18n -->

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic/logo.png" alt="uPic">
</div>

# ☁️ Terse image hosting client for Mac

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


## 📑 Introduction

> **uPic(upload Picture) is a image(file) hosting client for Mac.**
> You can upload images、files to specified provider’s OSD service which was configured.
> Before uploading, you can get an url immediately which can be accessed on internet. 



**💡 Tips：** They can automatic uploading local file and screenshot,meanwhile the menu bar shows the uploading progress constantly.File's link will automatically copied to the clipboard when finish upload,make you insert pictures quickly when you are blogging or chatting.Link’s format can be a normal URL,HTML or Markdown,it's totally up to you.

**🔋 Support image hosting：**[smms](https://sm.ms/)、 [UPYUN USS](https://www.upyun.com/products/file-storage)、[qiniu KODO](https://www.qiniu.com/products/kodo)、 [Aliyun OSS](https://www.aliyun.com/product/oss/)、 [TencentCloud COS](https://cloud.tencent.com/product/cos)、[Weibo](https://weibo.com/)、[Github](https://github.com/settings/tokens)、 [Gitee](https://gitee.com/profile/personal_access_tokens)、 [Amazon S3](https://aws.amazon.com/cn/s3/)、[custom upload api](https://blog.svend.cc/upic/tutorials/custom)、...

## 🚀 How to install


### 1.Homebrew:

``` bash
brew install bigwig-club/brew/upic --cask
```
### 2.Download from github
 click [release](https://github.com/gee1k/uPic/releases) to download.
 **If accessing Github is difficult to download, you can download it from [Gitee release](https://gitee.com/gee1k/uPic/releases).**

### Check Finder Extensions's authority

- 1.Run uPic

- 2.Open`system preference` - `extensions` - `Finder Extensions` make sure that `uPicFinderExtension` is be selected

  <center>
    <img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/finder-extension.png" height="300">
  </center>



## 🕹 How to use it

| Upload method | Description | Preview |
| ------------- | ----------- | ------- |
| **🖥 Select files** |  Select the file to upload from `Finder`.  `Can set global shortcuts`  | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/selectFile.gif) |
| **⌨️ Copy file upload** | Upload a file that has been copied to the clipboard.  `Can set global shortcuts` | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/pasteboard.gif) |
| **📸 Screenshot upload** | Directly pull frame screenshot upload.  `Can set global shortcuts` | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/screenshot.gif) |
| **🖱 Drag and drop local file upload** | Drag and drop files to the status bar to upload | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/dragFile.gif) |
| **🖱 Drag and drop browser image upload** | Drag image from browser to status bar to upload | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/dragFromBrowser.gif) |
| **📂 Finder contextmenu upload** | Right click on file upload | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/contextmenu.gif) |
| **⌨️ Command line upload** | Invoke uPic to upload files by executing commands | ![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/cli.gif) |



## 🧰 More Functions

### 1. Global shortcut key
<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/shortcuts.png" height="300">

### 2. Upload history
<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/screenshot/uPic-en/history.png" height="300">


## 📝 Tutorials

- [uPic configuration - Weibo](../tutorials/weibo/en)
- [uPic configuration - UPYUN](../tutorials/upyun_uss/en)
- [uPic configuration - Qiniu](../tutorials/qiniu_kodo/en)
- [uPic configuration - Aliyun](../tutorials/aliyun_oss/en)
- [uPic configuration - Tencent Cloud](../tutorials/tencent_cos/en)
- [uPic configuration - Baidu Cloud](../tutorials/baidu_bos/en)
- [uPic configuration - Amazon S3](../tutorials/amazon_s3/en)
- [uPic configuration - Github](../tutorials/github/en)
- [uPic configuration - Gitee(Gitee)](../tutorials/gitee/en)
- [uPic configuration - Imgur](../tutorials/imgur/en)
- [uPic configuration - Custom upload](../tutorials/custom/en)
- [uPic configuration - Chevereto](../tutorials/chevereto/en)

## 💌 Contact information

- `Email`: svend.jin@gmail.com
- `Telegram`: [gee1k](https://t.me/gee1k)
- `Github`: [Github](https://github.com/gee1k/uPic)
- `uPic chat group(Telegram)`:  [click here to join in](https://t.me/upic_host)

### Translators
- [@m01i0ng](https://github.com/m01i0ng)
- [@Jackxun123](https://github.com/Jackxun123)
- [@kkkkkkyrie](https://github.com/kkkkkkyrie)
