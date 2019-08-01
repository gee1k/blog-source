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
  <img src="https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/logo.png" alt="uPic">
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
brew cask install upic
```
### 2.Download from github
 click [release](https://github.com/gee1k/uPic/releases) to download.
 **If accessing Github is difficult to download, you can download it from [Gitee release](https://gitee.com/gee1k/uPic/releases).**

### Check Finder Extensions's authority

- 1.Run uPic

- 2.Open`system preference` - `extensions` - `Finder Extensions` make sure that `uPicFinderExtension` is be selected

  <center>
    <img src="https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-finder-extension.png" height="300">
  </center>



## 🕹 How to use it

| function | description | previewing |
| --- | --- | --- |
| **🖥 Pick** | choose file from `Finder` | ![](https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-selectFile.gif) |
| **⌨️ Copy** | uploud file from clipboard | ![](https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-paste.gif) |
| **🖱 Drag local file** | drag file to status bar | ![](https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-drag-finder.gif) |
| **🖱 Drag from browser** | drag image to status bar from browser | ![](https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-drag-browser.gif) |
| **📸 Screenshot** | capture a screenshot | ![](https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-screenshot.gif) |
| **📂 Right click** | right click to upload | ![](https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-finder-contextmenu.gif) |



## 🧰 More Functions

**Except these basic functions,uPic also provides a series of small features to improve user experience.**

<details><summary>1. ⌨︎ Global shortcut key</summary><br>
<p>
	<center>
		<img src="https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-shortcuts.png" height="300">
	</center>
</p>
</details>
<details><summary>2. 🕦 Upload history</summary><br>
<p>
	<center>
		<img src="https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-history.png" height="300">
	</center>
</p>
</details>
<details><summary>3. 📢 More functions are waiting for you to check it out</summary><br>
<p>
	...
</p>
</details>


## ❓ FAQ

<details>
	<summary>1.How to configurate image hosting❓</summary>
	<ul>
		<li><a href="https://blog.svend.cc/upic/tutorials/weibo/en" target="_blank">uPic configuration - Weibo</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/upyun_uss/en" target="_blank">uPic configuration - UPYUN</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/qiniu_kodo/en" target="_blank">uPic configuration - Qiniu</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/aliyun_oss/en" target="_blank">uPic configuration - Aliyun</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/tencent_cos/en" target="_blank">uPic configuration - TencentCloud</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/amazon_s3/en" target="_blank">uPic configuration - Amazon S3</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/github/en" target="_blank">uPic configuration - Github</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/gitee/en" target="_blank">uPic configuration - Gitee(Gitee)</a></li>
		<li><a href="https://blog.svend.cc/upic/tutorials/custom/en" target="_blank">uPic configuration - custom upload</a></li>
	</ul>
</details>
<details><summary>2. Finder extension doesn't work❓</summary><br>
<p>Because of Finder extension will always be selected after select action was done.So if you come across Finder extension operation is unresponsive,maybe uPic program was not runing.</p>
</details>
<details>
	<summary>3.Why I finished configuration of image hosting already,image/file upload failed?</summary>
	<div>
		<p>maybe you choose the wrong image hosting,go to check it out~</p>
		<img src="https://raw.githubusercontent.com/gee1k/oss/master/screenshot/uPic/en-default-host.png" width="450">
	</div> 
</details>


## 📝 Tutorials

- [uPic configuration - Weibo](./tutorials/weibo)
- [uPic configuration - UPYUN](./tutorials/upyun_uss)
- [uPic configuration - Qiniu](./tutorials/qiniu_kodo)
- [uPic configuration - Aliyun](./tutorials/aliyun_oss)
- [uPic configuration - Tencent Cloud](./tutorials/tencent_cos)
- [uPic configuration - Amazon S3](./tutorials/amazon_s3)
- [uPic configuration - Github](./tutorials/github)
- [uPic configuration - Gitee(Gitee)](./tutorials/gitee)
- [uPic configuration - Custom upload](./tutorials/custom)

## 💌 Contact information

- `Email`: svend.jin@gmail.com
- `Telegram`: [gee1k](https://t.me/gee1k)
- `Github`: [Github](https://github.com/gee1k/uPic)
- `uPic chat group(Telegram)`:  [click here to join in](https://t.me/upic_host)
- `Wechat group`:  <small>scan the QR code below to join in ↓ </small>

	<img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/geee1k.JPG" height="200">

### Translators
- [@m01i0ng](https://github.com/m01i0ng)
- [@Jackxun123](https://github.com/Jackxun123)
- [@kkkkkkyrie](https://github.com/kkkkkkyrie)


