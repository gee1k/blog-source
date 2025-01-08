---
title: uPic tutorial - Github
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

![Github configuration](https://r2.svend.cc/tutorials/github-host.png)

## 📝 Configuration item

- `Owner`: Github username.
   Example:My Github main page [https://github.com/gee1k](https://github.com/gee1k),my username is`gee1k`
- `Repo`: The name of repo which you want to upload files.
   Example:my Repo's URL=[https://github.com/gee1k/oss](https://github.com/gee1k/oss),and `oss` is the name of Reop.
- `Branch`: `master` is the name of Branch by default,if you want to upload to others,please establish first.
- `Token`: Github personal access tokens.
- `Domain`: You can't set domian name by default and will use your Github default URL.When you make the Rpeo's function of `pages` available and set up custom domain,you can use your own domain now.
  -  `Use the default CDN to speed access`: When checked, `jsdelivr` CDN is automatically used for accelerated access
- `Save Key`: The path to file storage (including folders). `Supports {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} and etc. For example, the uploaded file is uPic.jpg, set to \"uPic/{filename}{.suffix}\", it will be saved as: uPic/uPic.jpg.`


## 🔑 Token - How can I get it

- 1.Access [Github Token set page](https://github.com/settings/tokens/new)
- 2.Select `repo` access permission,then scroll to the bottom of the page,hit `Generate token` button to make token.
  ![创建 Token](https://r2.svend.cc/tutorials/github-token-2.png)
- 3.Copy the Token to uPic

**Attention：This Token shows one time only!Keep it carefully,otherwise you need reset one~**
  ![Copy Token](https://r2.svend.cc/tutorials/github-token-3.png)

## 🌝 Almost there!

**Save and choose the image hosting you configurate before on menu bar——image hosting bar,try to upload a image~**
**After successful upload,file/image will shows in your Github Repo**
![result](https://r2.svend.cc/tutorials/github-result.png)

<hr>

## 💌 Wechat chatting group
  <small> ↓scan the QR code below and join in the group!↓ </small> 

   <img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
