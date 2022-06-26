---
title: uPic tutorial - Imgur
date: 2019-08-18 16:03:43
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

![Imgur configuration](https://qiniu.svend.cc/tutorials/imgur-host.png)

## 📝 Configuration item

- `Client ID`: Applications Client ID

## 🔑 Client ID

- 1.Open [Imgur official website](https://imgur.com/) and login
- 2.Go to [Register Application](https://api.imgur.com/oauth2/addclient) page
- 3.Fill in the form information as required
- 4.**`Authorization type` option must select `OAuth 2 authorization without a callback URL`**
  ![Register Application](https://qiniu.svend.cc/tutorials/imgur-application.png)
- 5.Copy the generated Client ID value to the uPic and save it.
  ![Copy Client ID](https://qiniu.svend.cc/tutorials/imgur-client-id.png)
- 6.In the menu bar, select the Imgur host you just added. Try it out.

> The ClientID can be found directly in the [application list](https://imgur.com/account/settings/apps) next time.

<hr>
