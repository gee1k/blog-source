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

<hr><!-- i18n --><div align="right">**🇨🇳中文** | [**🇬🇧English**](./en)</div><!-- i18n -->

![自定义图床配置](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host.png)

## 📝 配置项说明

- `API 地址`: 后台服务 URL
- `请求方式`: 后台服务请求方式，支持`POST`和`PUT`
- `文件字段名`: 上传表单中的，文件对象的字段名
- `扩展字段`: Request Body。点击`其他字段`按钮进行配置
- `请求头`: Request Headers。点击`其他字段`按钮进行配置
- `URL 路径`: 上传完成返回的 JSON 中图片 URL 的获取路径。[获取规则](#URL-获取规则)
- `域名`: 上传过后，访问服务器文件的 URL。
- `更多设置`: `域名`后面设置按钮可以弹出详细的文件访问 URL 配置，可额外配置储存文件夹路径和文件名规则。
![其他字段](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host-extension-field.png)

![扩展配置](https://gitee.com/gee1k/oss/raw/master/tutorials/custom-host-extension.png)

<hr>

## URL 获取规则

- 例如：

```json
{
  "data": "http://xxx.png"
}

# 获取
["data"]
```

- 例如：

```json
{
  "data": {
    "url": "http://xxx.png"
  }
}
# 获取
["data", "url"]
```

- 例如：

```json
{
  "data": {
    "url": [
      "http://xxx.png"
    ]
  }
}

# 获取
["data", "url", 0]
```

- 例如：

```json
{
  "data": [
    {
      "url": "http://xxx.png"
    }
  ]
}

# 获取
["data", 0, "url"]

```

## 🏷 动态模板值

> 扩展字段和请求头都支持以下动态模板来获取动态值

- `{filename}`：会以上传时的文件名动态替换

## 💌 微信交流群
  <small>扫描下方二维码加好友拉你入群 ↓ </small>
	<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
```
