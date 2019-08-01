---
title: uPic tutorial - Upyun
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

<hr><!-- i18n --><div align="right">[**🇨🇳中文**](../)  | **🇬🇧English**</div><!-- i18n -->

![Upyun's config interface](https://gitee.com/gee1k/oss/raw/master/tutorials/upyun-host.png)

## 📝 Options instruction

- `Bucket`: The bucket name of oss space, you can find it in Upyun's control panel. [Example](#🧰-Region-domain)
- `Operate`: User who can access this namespace. [Example](#🔑-Operate-User-config)
- `Operate Password`: User's password. [Example](#🔑-Operate-User-config)
- `Domain`: You can custom your domain or use the default domain for testing provided by Upyun which can be found in Upyun's control panel. `Domain must start with http:// or https://`. [Example](#🧰-Region-domain)
- `More`: By clicking setting button after `Domain`, you can custom url/folder/patterns to access picture.
  - `Suffix`: This will be used for custom picture processor. You can configure it in Upyun's `图片处理-自定义版本`. Eg. Rule named `w` divided by `!` can apply watermark, so fill this field with `!w`. Then each generated url will have a suffix `-w`, which would carry a watermark.
  ![Extra](https://gitee.com/gee1k/oss/raw/master/tutorials/upyun-host-extension.png)

## 🧰 Region/domain

**Open [UPYUN Storage Service](https://console.upyun.com/services/file/)**
![Upyun control panel](https://gitee.com/gee1k/oss/raw/master/tutorials/upyun-info.png)

## 🔑 Operate User config

![Operate User config](https://gitee.com/gee1k/oss/raw/master/tutorials/upyun-operator.png)

<hr>

## 💌 Our Wechat group
  <small>Scan the qrcode to join the group ↓ </small>
	<img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
