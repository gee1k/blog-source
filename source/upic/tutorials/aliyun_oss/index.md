---
title: uPic 图床配置教程 - 阿里云
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

<hr>

![阿里云配置](https://gitee.com/gee1k/oss/raw/master/tutorials/aliyun-host.png)

## 📝 配置项说明

- `区域`: 对象储存空间所属的区域，可在阿里云控制台查看。[图例](#🧰-区域、空间名称、域名信息获取)
- `空间名称`: 对象储存空间名称，可在阿里云控制台查看。[图例](#🧰-区域、空间名称、域名信息获取)
- `Access Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `Secret Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `域名`: 使用阿里云默认提供的测试域名或者你的自定义域名。域名可在控制台查看。`域名需以http://或者https://开头`。[图例](#🧰-区域、空间名称、域名信息获取)
- `更多设置`: `域名`后面设置按钮可以弹出详细的文件访问 URL 配置，可额外配置储存文件夹路径和文件名规则。
  ![扩展配置](https://gitee.com/gee1k/oss/raw/master/tutorials/aliyun-host-extension.png)

## 🧰 区域、空间名称、域名信息获取

**进入 [云存储](https://oss.console.aliyun.com/overview) 控制台查看**
`注意读写权限需要设置可公共读取，不然上传完成之后无法通过 URL 访问哦。可在存储空间的基础设置里更改权限。`
![阿里云控制台](https://gitee.com/gee1k/oss/raw/master/tutorials/aliyun-info.png)

## 🔑 密钥获取(AccessKey ID、Access Key Secret)

**进入个人中心 [用户信息管理](https://usercenter.console.aliyun.com/#/manage/ak) 查看**
![密钥](https://gitee.com/gee1k/oss/raw/master/tutorials/aliyun-ak.png)

<hr>

## 微信交流群
  <small>扫描下方二维码加好友拉你入群 ↓ </small>
	<img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
