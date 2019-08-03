---
title: uPic tutorial - Amazon S3
date: 2019-07-30 20:33:43
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

![Amazon S3 config](https://gitee.com/gee1k/oss/raw/master/tutorials/amazon_s3-host.png)

## 📝 Options instruction

- `Region`: The region of your Amazon S3,can be viewed in the Amazon S3 console panel.[Example](#🧰-Region-bucket-domain)
- `Bucket`: The bucket name of your Amazon S3,can be viewed in the Amazon S3 console panel.[Example](#🧰-Region-bucket-domain)
- `Access Key`: The Access Key of Amazon S3. [Example](#🔑-The-Secret-AccessKey-ID、Access-Key-Secret)
- `Secret Key`: The Secret Key of Amazon S3. [Example](#🔑-The-Secret-AccessKey-ID、Access-Key-Secret)
- `Domain`: Amazon S3 has default domain names. don't have to
- `More`: By clicking setting button after `Domain`, you can custom url/folder/patterns to access picture.
  - `Suffix`: For custom image processing. Amazon S3 is not currently supported, so reserve it first
    ![extension config](https://gitee.com/gee1k/oss/raw/master/tutorials/amazon_s3-host-extension.png)

## 🧰 Region/bucket/domain

**View it by  open [Cloud storage](https://s3.console.aws.amazon.com/s3) console panel**
`Pay attention here!! when creating a bucket, don't check the permission settings to block all public access.`
![Amazon S3 console](https://gitee.com/gee1k/oss/raw/master/tutorials/amazon_s3-info.png)

## 🔑 The Secret(AccessKey ID、Access Key Secret)

**get it by open console panel `My security credentials` -> `Access key (access key ID and secret access key)` **

- It is recommended to use Amazon's [IAM](https://docs.aws.amazon.com/zh_cn/IAM/latest/UserGuide/introduction.html) to create AccessKey ID and AccessKey Secret. Can better set key permissions, more secure

<hr>

## 💌 Our Wechat group

  <small>↓scan the QR code below and join in the group!↓ </small>
	<img src="https://raw.githubusercontent.com/gee1k/oss/master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>

