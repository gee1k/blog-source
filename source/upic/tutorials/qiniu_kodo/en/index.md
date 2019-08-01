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

![Qiniu's config interface](https://gitee.com/gee1k/oss/raw/master/tutorials/qiniu-host.png)

## 📝 Options instruction

- `Region`: Where your storage space located, you can find it in Qiniu's control panel. [Example](#🧰-Region-bucket-domain)
- `Bucket`: The bucket name of your storage space, can be found in Qiniu's control panel. [Example](#🧰-Region-bucket-domain)
- `Access Key`: Access key provided by Qiniu. [Example](#🔑-Secret-Access-Key、Secret-Key)
- `Secret Key`: Secret key provided by Qiniu. [Example](#🔑-Secret-Access-Key、Secret-Key)
- `Domain`: You can custom your domain or use the default domain for testing provided by Qiniu which can be found in Qiniu's control panel.`Domain must start with http:// or https://`. [Example](#🧰-Region-bucket-domain)
- `More`: By clicking setting button after `Domain`, you can custom url/folder/patterns to access picture.
  - `Suffix`: This can be used for custom picture processor. You can configure custom picture style via Qiniu. Eg. Rule named `w` divided by `!` can apply watermark, so fill this field with `!w`. Then each generated url will have a suffix `-w`, which would carry a watermark.
  ![Extra](https://gitee.com/gee1k/oss/raw/master/tutorials/qiniu-host-extension.png)

## 🧰 Region/bucket/domain

**Open [OSS](https://portal.qiniu.com/bucket) control panel**
![Qiniu's control panel](https://gitee.com/gee1k/oss/raw/master/tutorials/qiniu-info.png)

## 🔑 Secret(Access Key、Secret Key)

**View it by entering personal info [Secret](https://portal.qiniu.com/user/key)**

![Secret](https://gitee.com/gee1k/oss/raw/master/tutorials/qiniu-ak.png)

<hr>

## 💌 Our Wechat group
  <small>Scan the qrcode to join the group ↓ </small>
	<img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
