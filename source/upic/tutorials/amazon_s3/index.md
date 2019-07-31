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

<hr>

![Amazon S3配置](https://gitee.com/gee1k/oss/raw/master/tutorials/amazon_s3-host.png)

## 📝 配置项说明

- `区域`: 对象储存空间所属的区域，可在Amazon S3控制台查看。[图例](#🧰-区域、空间名称获取)
- `空间名称`: 对象储存空间名称，可在Amazon S3控制台查看。[图例](#🧰-区域、空间名称获取)
- `Access Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `Secret Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `域名`: 使用 Amazon S3 有默认提供的域名。可以不填写
- `更多设置`: `域名`后面设置按钮可以弹出详细的文件访问 URL 配置，可额外配置储存文件夹路径和文件名规则。
  - `网址后缀`: 用于自定义图片处理。Amazon S3 目前还不支持，先预留
  ![扩展配置](https://gitee.com/gee1k/oss/raw/master/tutorials/amazon_s3-host-extension.png)

## 🧰 区域、空间名称获取

**进入 [云存储](https://s3.console.aws.amazon.com/s3) 控制台查看**
`注意创建 bucket 的时候权限设置不要勾选阻止所有公共访问。`
![Amazon S3控制台](https://gitee.com/gee1k/oss/raw/master/tutorials/amazon_s3-info.png)

## 🔑 密钥获取(AccessKey ID、Access Key Secret)

**进入控制台`我的安全凭证` -> `访问密钥(访问密钥 ID 和秘密访问密钥)` 获取**
- 推荐使用 Amazon 的 [IAM](https://docs.aws.amazon.com/zh_cn/IAM/latest/UserGuide/introduction.html) 来创建 AccessKey ID、Access Key Secret。可更好的设置密钥权限，更为安全

<hr>

## 💌 微信交流群
  <small>扫描下方二维码加好友拉你入群 ↓ </small>
	<img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
