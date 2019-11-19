---
title: uPic 图床配置教程 - 百度云
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

![百度云配置](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-host.png)

## 📝 配置项说明

- `区域`: 对象储存空间所属的区域，可在百度云控制台查看。[图例](#🧰-区域、空间名称、域名信息获取)
- `空间名称`: 对象储存空间名称，可在百度云控制台查看。[图例](#🧰-区域、空间名称、域名信息获取)
- `Access Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `Secret Key`: 密钥。[图例](#🔑-密钥获取-AccessKey-ID、Access-Key-Secret)
- `域名`: 使用百度云默认提供的测试域名或者你的自定义域名。域名可在控制台查看。`域名需以http://或者https://开头`。[图例](#🧰-区域、空间名称、域名信息获取)
- `更多设置`: `域名`后面设置按钮可以弹出详细的文件访问 URL 配置，可额外配置储存文件夹路径和文件名规则。
  - `网址后缀`: 用于自定义图片处理。在百度云对象储存中可以配置`图片处理域名规则`。例如：规则名称为`w`的规则来标识水印版本，分隔符为`@!`，则可以在网址后缀中填写`@!w`。之后每次上传的图片生成连接后面都会追加上`@!w`，即表示访问水印版本。
  ![扩展配置](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-host-extension.png)

## 🧰 区域、空间名称、域名信息获取

**进入 [云存储](https://console.bce.baidu.com/bos) 控制台查看**
`注意读写权限需要设置可公共读取，不然上传完成之后无法通过 URL 访问哦。可在存储空间的基础设置里更改权限。`
![百度云控制台](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-info.jpg)

## 🔑 密钥获取(AccessKey ID、Access Key Secret)

**进入个人中心 [用户信息管理](https://console.bce.baidu.com/iam/#/iam/accesslist) 查看**
![密钥](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-ak.jpg)

<hr>

## 💌 微信交流群
  <small>扫描下方二维码加好友拉你入群 ↓ </small>
	<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
