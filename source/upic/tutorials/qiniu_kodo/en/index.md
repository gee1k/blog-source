---
title: uPic tutorial - Qiniu
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

![Qiniu's config interface](https://r2.svend.cc/tutorials/qiniu-host.png)

## 📝 Options instruction

- `Region`: Where your storage space located, you can find it in Qiniu's control panel. [Example](#🧰-Region-bucket-domain)
- `Bucket`: The bucket name of your storage space, can be found in Qiniu's control panel. [Example](#🧰-Region-bucket-domain)
- `Access Key`: Access key provided by Qiniu. [Example](#🔑-Secret-Access-Key、Secret-Key)
- `Secret Key`: Secret key provided by Qiniu. [Example](#🔑-Secret-Access-Key、Secret-Key)
- `Domain`: You can custom your domain or use the default domain for testing provided by Qiniu which can be found in Qiniu's control panel.`Domain must start with http:// or https://`. [Example](#🧰-Region-bucket-domain)
- `Save Key`: The path to file storage (including folders). `Supports {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} and etc. For example, the uploaded file is uPic.jpg, set to \"uPic/{filename}{.suffix}\", it will be saved as: uPic/uPic.jpg.`
- `The after Save Key input is Suffix`: This will be used for custom picture processor. You can configure custom `picture style` via Qiniu. Eg. Rule named w divided by ! can apply watermark, so fill this field with !w. Then each generated url will have a suffix -w, which would carry a watermark.

## 🧰 Region/bucket/domain

**Open [OSS](https://portal.qiniu.com/bucket) control panel**
![Qiniu's control panel](https://r2.svend.cc/tutorials/qiniu-info.png)

## 🔑 Secret(Access Key、Secret Key)

**View it by entering personal info [Secret](https://portal.qiniu.com/user/key)**

![Secret](https://r2.svend.cc/tutorials/qiniu-ak.png)

<hr>
