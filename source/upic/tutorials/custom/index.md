---
title: uPic 图床配置教程 - 自定义
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

![自定义图床配置](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host.png)

## 📝 配置项说明

- `API 地址`: 后台服务 URL
- `请求方式`: 后台服务请求方式，支持`POST`和`PUT`
- `文件字段名`: 上传表单中的，文件对象的字段名
- `扩展字段`: 上传表单中的额外属性。`key=value&key2=value2`
- `请求头`: Request Headers。`key=value&key2=value2`
- `域名`: 上传过后，访问服务器文件的 URL。
- `更多设置`: `域名`后面设置按钮可以弹出详细的文件访问 URL 配置，可额外配置储存文件夹路径和文件名规则。

![扩展配置](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host-extension.png)
<hr>

## 🏷 动态模板值
> 扩展字段和请求头都支持以下动态模板来获取动态值 

- `{filename}`：会以上传时的文件名动态替换
- `{folder}`：会以更多设置中配置的`folder`动态替换
- `{path}`：会以上传时的完整的`folder/文件名`动态替换

## uPic 微信交流群

  <img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/uPic-wechat.JPG" alt="uPic产品交流群" style="width: 300px;" align="center">

<hr>
