---
title: uPic tutorial - Tencent Cloud
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

![Tencent Cloud's config interface](https://gitee.com/gee1k/oss/raw/master/tutorials/tencent-host.png)

## 📝 Options instruction

- `Region`: Where your oss space located, can be found in tencent cloud's control panel. [Example](#🧰-Region-bucket-domain)
- `Bucket`: The bucket name of your oss space, can be found in tencent cloud's control panel. [Example](#🧰-Region-bucket-domain)
- `SecretId`: SecretId provided by tencent cloud. [Example](#🔑-Secret-SecretId、SecretKey)
- `SecretKey`: Secret Key provided by tencent cloud. [Example](#🔑-Secret-SecretId、SecretKey)
- `Domain`: You can custom your domain or use the default domain for testing provided by tencent cloud which can be found in tencent cloud's control panel. `Domain must start with http:// or https://`. [Example](#🧰-Region-bucket-domain)
- `Save Key`: The path to file storage (including folders). `Supports {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} and etc. For example, the uploaded file is uPic.jpg, set to \"uPic/{filename}{.suffix}\", it will be saved as: uPic/uPic.jpg.`
- `The after Save Key input is Suffix`: For custom image processing. Tentcent COS is not currently supported, so reserve it first.

## 🧰 Region/bucket/domain

**Open [Bucket](https://console.cloud.tencent.com/cos5/bucket) control panel, create and configure bucket**

![Base info](https://gitee.com/gee1k/oss/raw/master/tutorials/tencent-info.png)

`Pay attention here!! Your bucket permission must be set Public Read, otherwise the picture couldn't be access via uel. Configure it carefully by enter this link.`
![Permission](https://gitee.com/gee1k/oss/raw/master/tutorials/tencent-info-2.png)

## 🔑 Secret(SecretId、SecretKey)

**View it by entering personal info [Secret](https://console.cloud.tencent.com/cam/capi)**
![Secret](https://gitee.com/gee1k/oss/raw/master/tutorials/tencent-ak.png)

<hr>
