---
title: uPic tutorial - baidu BOS
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

<hr><!-- i18n --><div align="right">[**🇨🇳中文**](../) | **🇬🇧English**</div><!-- i18n -->

![baidu cloud configuration](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-host.png)

## 📝 Options instruction

- `Region`: The region of your baidu cloud,can be viewed in the baidu cloud's console panel.[Example](#🧰-Region-bucket-domain)
- `Bucket`: The bucket name of your baidu cloud,can be viewed in the baidu cloud's console panel. [Example](#🧰-Region-bucket-domain)
- `Access Key`: The Access Key of baidu cloud. [Example](#🔑-The-Secret-AccessKey-ID、Access-Key-Secret)
- `Secret Key`: The Secret Key of baidu cloud. [Example](#🔑-The-Secret-AccessKey-ID、Access-Key-Secret)
- `Domain`: You can custom your domain or use the default domain for test provided by baidu cloud, can be found in baidu cloud's control panel.`Domain must start with http:// or https://`.[Example](#🧰-Region-bucket-domain)
- `More`: By clicking setting button after `Domain`, you can custom url/folder/patterns to access picture.
  - `Suffix`: For custom image processing. There can be configured `image processing domain name rules` in baidu cloud. For example, if the rule name is `w` to identify the watermark version and the separator is `!`, you can fill in the URL suffix `!w`. After each uploaded image generation connection will be appended with `-w`, that is, to access the watermark version.
  - ![extension](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-host-extension.png)

## 🧰 Region/bucket/domain

**View it by entering  [Cloud storage](https://console.bce.baidu.com/bos) console panel**

`Pay attention here!! Your bucket permission must be set Public Read, otherwise the picture couldn't be access via uel. Configure it carefully by enter this link.`
![baidu cloud console](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-info.jpg)



## 🔑 The Secret(AccessKey ID、Access Key Secret)

**View it by entering personal info  [User information management](https://console.bce.baidu.com/iam/#/iam/accesslist) console panel**
![AccessKey](https://gitee.com/gee1k/oss/raw/master/tutorials/baidu-ak.jpg)

<hr>
## 💌 Our Wechat group
  <small>Scan the qrcode to join the group ↓ </small>
​	<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>

