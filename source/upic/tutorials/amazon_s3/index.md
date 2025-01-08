---
title: uPic 图床配置教程 - Amazon S3
date: 2019-07-30 20:33:43
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

![Amazon S3配置](https://r2.svend.cc/tutorials/amazon_s3-host.png)

## 📝 配置项说明

- `区域`: 对象储存空间所属的区域，可在Amazon S3控制台查看。[图例](#🧰-区域、空间名称获取)
- `空间名称`: 对象储存空间名称，可在Amazon S3控制台查看。[图例](#🧰-区域、空间名称获取)
- `Access Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `Secret Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `域名`: 使用 Amazon S3 有默认提供的域名。可以不填写
- `保存路径`: 文件储存的路径（包括文件夹）。 `支持 {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} 等变量。比如：上传的图片为 uPic.jpg，设定为 “uPic/{filename}{.suffix}”，则会保存到 “uPic/uPic.jpg”。`
- 在`保存路径`输入框后面的是`网址后缀`: 用于自定义图片处理。Amazon S3 目前还不支持，先预留。

## 🧰 区域、空间名称获取

**进入 [云存储](https://s3.console.aws.amazon.com/s3) 控制台查看**

**⚠️ 注意: **
- 1.bucket 名称不要以类似：`blog.svend.cc` 的格式来命名，这样的 bucket 名称 S3 分配的链接会是`https://s3.ap-northeast-2.amazonaws.com/blog.svend.cc/uPic.txt`，而不是子域名。会导致上传失败。应当以类似：`blog-svend-cc` 的格式来命名，S3 分配的链接则会是以子域名生成：`https://blog-svend-cc.s3.ap-northeast-2.amazonaws.com/uPic.txt`
- 2.创建 bucket 的时候权限设置不要勾选阻止所有公共访问。

![Amazon S3控制台](https://r2.svend.cc/tutorials/amazon_s3-info.png)

## 🔑 密钥获取(AccessKey ID、Access Key Secret)

**进入控制台`我的安全凭证` -> `访问密钥(访问密钥 ID 和秘密访问密钥)` 获取**
- 推荐使用 Amazon 的 [IAM](https://docs.aws.amazon.com/zh_cn/IAM/latest/UserGuide/introduction.html) 来创建 AccessKey ID、Access Key Secret。可更好的设置密钥权限，更为安全

<hr>
