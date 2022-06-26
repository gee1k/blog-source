---
title: uPic 图床配置教程 - Chevereto
date: 2020-04-02 20:03:43
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

> 近期很多用户反应 Chevereto 用来搭建图床很好用，但是 uPic 里无法配置成功。
> 所以写一篇 uPic 通过自定义图床配置 Chevereto 的教程。`需 uPic v0.18.2 及以后`

## 📝 配置参数准备

- `上传服务地址`: `[你的 Chevereto 地址]/api/1/upload`。例如 `https://demo.chevereto.com/api/1/upload`
- `API Key`: 在浏览器登录你的 Chevereto 后，打开`仪表盘`->`设置`->`API`。拷贝 API v1 Key

## 基础配置

- `API 地址`: 填写上面准备好的 `[上传服务地址]`
- `请求方式`:  `POST`
- `使用 Base64`:  `勾选`
- `文件字段名`: `source`
- `URL 路径`: 上传完成后获取图片链接的路径。`['image', 'url']`


![基础配置](https://qiniu.svend.cc/tutorials/chevereto_host.jpg)

## 扩展配置

### Headers
- `Content-Type`: `multipart/form-data; charset=utf-8;`

### Bodys
- `key`: 填写上面准备好的 `[API Key]`
- `action`: `upload`

![扩展配置](https://qiniu.svend.cc/tutorials/chevereto_host_extension.jpg)

<hr>
