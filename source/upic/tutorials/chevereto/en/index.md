---
title: uPic tutorial - Chevereto
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

<hr><!-- i18n --><div align="right">[**🇨🇳中文**](../) | **🇬🇧English**</div><!-- i18n -->

> Recently, many users have commented that Chevereto is very good for building the image bed, but it cannot be configured successfully in uPic.
> So write a tutorial on uPic configuring Chevereto with a custom map bed. 'need uPic v0.18.2 and later'

## 📝 Options instruction

- `Upload URL`: `[Your Chevereto domain]/api/1/upload`。eg: `https://demo.chevereto.com/api/1/upload`
- `API Key`: After the browser logs into your Chevereto, open 'dashboard' -> 'settings' -> 'API'. Copy the API v1 Key

## Basic configuration

- `API URL`: `[Upload URL]`
- `Method`:  `POST`
- `Use Base64`:  `Check`
- `File Field`: `source`
- `URL Path`: `['image', 'url']`


![Basic configuration](https://qiniu.svend.cc/tutorials/chevereto_host_en.jpg)

## Extension configuration

### Headers
- `Content-Type`: `multipart/form-data; charset=utf-8;`

### Bodys
- `key`: `[API Key]`
- `action`: `upload`

![Extension configuration](https://qiniu.svend.cc/tutorials/chevereto_host_extension_en.jpg)

<hr>
