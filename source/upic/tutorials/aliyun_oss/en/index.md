---
title: uPic tutorial - aliyun
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

![Aliyun configuration](https://qiniu.svend.cc/tutorials/aliyun-host.png)

## 📝 Options instruction

- `Region`: The region of your aliyun,can be viewed in the aliyun console panel.[Example](#🧰-Region-bucket-domain)
- `Bucket`: The bucket name of your aliyun,can be viewed in the aliyun console panel. [Example](#🧰-Region-bucket-domain)
- `Access Key`: The Access Key of aliyun. [Example](#🔑-The-Secret-AccessKey-ID、Access-Key-Secret)
- `Secret Key`: The Secret Key of aliyun. [Example](#🔑-The-Secret-AccessKey-ID、Access-Key-Secret)
- `Domain`: You can custom your domain or use the default domain for test provided by aliyun, can be found in aliyun's control panel.`Domain must start with http:// or https://`.[Example](#🧰-Region-bucket-domain)
- `Save Key`: The path to file storage (including folders). `Supports {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} and etc. For example, the uploaded file is uPic.jpg, set to \"uPic/{filename}{.suffix}\", it will be saved as: uPic/uPic.jpg.`
- `The after Save Key input is Suffix`: For custom image processing. There can be configured `image processing rules` in aliyun. For example, if the rule name is w to identify the watermark version and the separator is !, you can fill in the URL suffix !w. After each uploaded image generation connection will be appended with -w, that is, to access the watermark version.

## 🧰 Region/bucket/domain

**View it by entering  [Cloud storage](https://oss.console.aliyun.com/overview) console panel**

`Pay attention here!! Your bucket permission must be set Public Read, otherwise the picture couldn't be access via uel. Configure it carefully by enter this link.`
![Aliyun console](https://qiniu.svend.cc/tutorials/aliyun-info.png)



## 🔑 The Secret(AccessKey ID、Access Key Secret)

**View it by entering personal info  [User information management](https://usercenter.console.aliyun.com/#/manage/ak) console panel**
![AccessKey](https://qiniu.svend.cc/tutorials/aliyun-ak.png)

<hr>
