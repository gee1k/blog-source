---
title: uPic tutorial - Weibo
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

![Weibo's config interface](https://qiniu.svend.cc/tutorials/weibo-host.png)

## 📝 Options instruction

- `Cookie Mode`: Select to enable `Cookie Mode`, otherwise `Username/Password Mode` will be enabled.
- `Username`: Weibo account.
- `Password`: Weibo password.
  - `When Cookie Mode wasn't enabled, uPic will use username and password to achieve cookie to upload your picture.`
- `Cookie`: Cookie configured manually.
  - `When Cookie Mode was enabled, uPic will use this cookie to upload your picture.`
- `Quality`: Weibo can provide three picture quality to select: `Origin(large)`、`Middle(mw690)`、`Thumbnail(thumbnail)`.
  - `The picture's quality in Weibo server won't be effected, it just provide three urls to access different quality of picture.`

## 🔑 The method to achieve Cookie

> This will be needed only when Cookie Mode was enabled.

![Achieve Cookie](https://qiniu.svend.cc/tutorials/weibo-get-cookie.png)

- 1.Login Weibo in your browser(Chrome recommended), open <a href="https://weibo.com/minipublish" target="_blank">minipublish page</a>. `It could be very simple to catch a request to achieve cookie in this page due to less content.`
- 2.Open developer tool by press `command + option + i`, switch to `Network` tab.
- 3.Refresh page and developer tool will catch requests, select `minipublish` request, it can be the first one usually.
- 4.Then pay attention to `Headers` section right, find out the content as above picture's red box selected.
- 5.Copy the content and paste it into uPic's `Cookie` field.

## ⚖️ Two methods' difference

- `Username/Password Mode`: Can achieve cookie automatically by call Weibo's api and do upload. But because of its extra request, it can be a bit slow.
- `Cookie Mode`: More faster. But it can be a bit difficult for rookie.

> Either method is ok, you can choose the one you favorite.

<hr>
