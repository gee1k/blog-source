---
title: uPic 图床配置教程 - Imgur
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

<hr><!-- i18n --><div align="right">**🇨🇳中文** | [**🇬🇧English**](./en)</div><!-- i18n -->

![Imgur 配置](https://r2.svend.cc/tutorials/imgur-host.png)

## 📝 配置项说明

- `Client ID`: Applications Client ID

## 🔑 Client ID 获取方式

- 1.打开[Imgur 官网](https://imgur.com/)并登陆
- 2.进入[应用注册](https://api.imgur.com/oauth2/addclient)页面
- 3.按要求填写表单信息
- 4.注意`Authorization type`选项必须选择`OAuth 2 authorization without a callback URL`
  ![注册 Application](https://r2.svend.cc/tutorials/imgur-application.png)
- 5.复制生成好的 Client ID 值到 uPic Client ID 输入框并保存
  ![复制 Client ID](https://r2.svend.cc/tutorials/imgur-client-id.png)
- 6.在菜单栏中选择刚刚添加的 Imgur 上传图片试试吧

> 下次可直接在[应用列表](https://imgur.com/account/settings/apps)里找到 ClientID

<hr>
