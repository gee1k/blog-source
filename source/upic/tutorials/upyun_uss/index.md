---
title: uPic 图床配置教程 - 又拍云
date: 2019-07-01 21:03:43
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

<hr><!-- i18n --><div align="right">**🇨🇳中文** | [**🇬🇧English**](./en)</div><!-- i18n -->

![又拍云配置](https://gitee.com/gee1k/oss/raw/master/tutorials/upyun-host.png)

## 📝 配置项说明

- `空间名称`: 对象储存空间名称，可在又拍云控制台查看。[图例](#🧰-空间名称、域名信息获取)
- `操作员`: 当前空间授权过的操作员。[图例](#🔑-操作人员配置)
- `操作员密码`: 对应的操作员密码。[图例](#🔑-操作人员配置)
- `域名`: 使用又拍云默认提供的测试域名或者你的自定义域名。测试域名可在控制台查看。`域名需以http://或者https://开头`。[图例](#🧰-空间名称、域名信息获取)
- `保存路径`: 文件储存的路径（包括文件夹）。 `支持 {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} 等变量。比如：上传的图片为 uPic.jpg，设定为 “uPic/{filename}{.suffix}”，则会保存到 “uPic/uPic.jpg”。`
- 在`保存路径`输入框后面的是`网址后缀`: 用于自定义图片处理。在又拍云对象储存中可以配置`图片处理-自定义版本`。例如：规则名称为`w`的规则来标识水印版本，分隔符为`!`，则可以在网址后缀中填写`!w`。之后每次上传的图片生成连接后面都会追加上`-w`，即表示访问水印版本。

## 🧰 空间名称、域名信息获取

**进入 [云存储](https://console.upyun.com/services/file/) 控制台查看**
![又拍云控制台](https://gitee.com/gee1k/oss/raw/master/tutorials/upyun-info.png)

## 🔑 操作人员配置

![操作人员配置](https://gitee.com/gee1k/oss/raw/master/tutorials/upyun-operator.png)

<hr>

## 💌 微信交流群
  <small>扫描下方二维码加好友拉你入群 ↓ </small>
	<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
