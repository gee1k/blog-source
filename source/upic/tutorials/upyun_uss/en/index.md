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

![Upyun's config interface](https://r2.svend.cc/tutorials/upyun-host.png)

## 📝 Options instruction

- `Bucket`: The bucket name of oss space, you can find it in Upyun's control panel. [Example](#🧰-Region-domain)
- `Operate`: User who can access this namespace. [Example](#🔑-Operate-User-config)
- `Operate Password`: User's password. [Example](#🔑-Operate-User-config)
- `Domain`: You can custom your domain or use the default domain for testing provided by Upyun which can be found in Upyun's control panel. `Domain must start with http:// or https://`. [Example](#🧰-Region-domain)
- `Save Key`: The path to file storage (including folders). `Supports {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} and etc. For example, the uploaded file is uPic.jpg, set to \"uPic/{filename}{.suffix}\", it will be saved as: uPic/uPic.jpg.`
- `The after Save Key input is Suffix`: This will be used for custom picture processor. You can configure it in Upyun's `图片处理-自定义版本`. Eg. Rule named `w` divided by `!` can apply watermark, so fill this field with `!w`. Then each generated url will have a suffix `-w`, which would carry a watermark.

## 🧰 Region/domain

**Open [UPYUN Storage Service](https://console.upyun.com/services/file/)**
![Upyun control panel](https://r2.svend.cc/tutorials/upyun-info.png)

## 🔑 Operate User config

![Operate User config](https://r2.svend.cc/tutorials/upyun-operator.png)

<hr>
