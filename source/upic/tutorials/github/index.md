---
title: uPic 图床配置教程 - Github
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

<hr><!-- i18n --><div align="right">**🇨🇳中文** | [**🇬🇧English**](./en)</div><!-- i18n -->

![Github 配置](https://gitee.com/gee1k/oss/raw/master/tutorials/github-host.png)

## 📝 配置项说明

- `用户名`: Github 用户名。例如：我的 Github 主页[https://github.com/gee1k](https://github.com/gee1k)，我的用户名就是`gee1k`
- `仓库名`: 需要储存上传文件的仓库名称。例如：我的仓库地址为 [https://github.com/gee1k/oss](https://github.com/gee1k/oss)，仓库名称就是`oss`
- `分支`: 分支名称，默认是`master`，如果是其他分支，就必须先创建好分支，才能上传
- `Token`: Github 的个人访问令牌（Personal access tokens）
- `域名`: 默认可不设置域名，会使用 Github 默认的访问地址。当你的仓库开启了`pages`功能，并配置好了自定义域名时，这里就可以使用你的自定义域名
  -  `使用默认 CDN 加速访问`: 勾选时会自动使用 `jsdelivr` CDN 进行加速访问 
- `保存路径`: 文件储存的路径（包括文件夹）。 `支持 {year} {month} {day} {hour} {minute} {second} {since_second} {since_millisecond} {random} {filename} {.suffix} 等变量。比如：上传的图片为 uPic.jpg，设定为 “uPic/{filename}{.suffix}”，则会保存到 “uPic/uPic.jpg”。`

## 🔑 Token 获取方式

- 1.进入[Github Token 创建页面](https://github.com/settings/tokens/new)
- 2.勾选 `repo` 访问权限。然后滚动页面到底部，点击`Generate token`按钮来生成 token
  ![创建 Token](https://gitee.com/gee1k/oss/raw/master/tutorials/github-token-2.png)
- 3.复制生成好的 Token 值到 uPic token 输入框
  **注意：此 Token 只会显示一次！请务必保存好，否则之后丢失了，就得重新创建了~ **
  ![复制 Token](https://gitee.com/gee1k/oss/raw/master/tutorials/github-token-3.png)

## 🌝 最终效果

**保存一下，在菜单栏-图床栏选中刚刚配置好的 Github 图床，上传一张图片试试吧~**
**上传成功后，Github 仓库就会出现你刚上传的文件啦**
![结果](https://gitee.com/gee1k/oss/raw/master/tutorials/github-result.png)

<hr>

## 💌 微信交流群
  <small>扫描下方二维码加好友拉你入群 ↓ </small>
	<img src="https://cdn.jsdelivr.net/gh/gee1k/oss@master/personal/geee1k.JPG" height="200" style="height:200px">

<hr>
