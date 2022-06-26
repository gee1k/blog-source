---
title: uPic 图床配置教程 - 腾讯云
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

![腾讯云配置](https://qiniu.svend.cc/tutorials/tencent-host.png)

## 📝 配置项说明

- `区域`: 对象储存空间所属的区域，可在腾讯云控制台查看。[图例](#🧰-区域、空间名称、域名信息获取)
- `空间名称`: 对象储存空间名称，可在腾讯云控制台查看。[图例](#🧰-区域、空间名称、域名信息获取)
- `SecretId`: 密钥。[图例](#🔑-密钥获取-SecretId、SecretKey)
- `SecretKey`: 密钥。[图例](#🔑-密钥获取-SecretId、SecretKey)
- `域名`: 使用腾讯云默认提供的测试域名或者你的自定义域名。域名可在控制台查看。`域名需以http://或者https://开头`。[图例](#🧰-区域、空间名称、域名信息获取)
- `保存路径`: 文件储存的路径（包括文件夹）。 `支持 {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} 等变量。比如：上传的图片为 uPic.jpg，设定为 “uPic/{filename}{.suffix}”，则会保存到 “uPic/uPic.jpg”。`
- 在`保存路径`输入框后面的是`网址后缀`: 用于自定义图片处理。腾讯云 COS 目前还不支持，先预留。

## 🧰 区域、空间名称、域名信息获取

**进入 [储存桶](https://console.cloud.tencent.com/cos5/bucket) 控制台，创建并进入储存桶详情页**

![基本信息](https://qiniu.svend.cc/tutorials/tencent-info.png)

`注意读写权限需要设置可公共读取，不然上传完成之后无法通过 URL 访问哦。可在存储空间的基础设置里更改权限。`
![权限设置](https://qiniu.svend.cc/tutorials/tencent-info-2.png)

## 🔑 密钥获取(SecretId、SecretKey)

**进入个人中心 [密钥管理](https://console.cloud.tencent.com/cam/capi) 查看**
![密钥](https://qiniu.svend.cc/tutorials/tencent-ak.png)

<hr>
