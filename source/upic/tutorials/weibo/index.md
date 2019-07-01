---
title: uPic 图床配置教程 - 微博
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

![微博配置界面](https://gitee.com/gee1k/oss/raw/master/tutorials/weibo-host.png)

## 📝 配置项说明

- `Cookie 模式`: 选中启用 Cookie 模式，否则使用用户名、密码模式
- `用户名`: 微博登录账号。
- `密码`: 微博登录密码。
  - `当未选择 Cookie 模式时，将会使用用户名、密码进行自动调用登录接口并获取 Cookie 进行上传`
- `Cookie`: 手动配置微博登录之后的 Cookie 值。
  - `当选择 Cookie 模式时，将会使用此 Cookie 进行上传`
- `图片质量`: 微博提供三种质量的图片供选择使用：`原图(large)`、`中等尺寸(mw690)`、`缩略图(thumbnail)`。
  - `并不会影响上传到服务器的图片，只是访问的 URL 不同，随时都可通过改变 URL 参数进行访问其他的清晰度`

## 🔑 Cookie 获取方式

> 当选择 Cookie 模式时才需要手动获取哦

![获取 Cookie](https://gitee.com/gee1k/oss/raw/master/tutorials/weibo-get-cookie.png)

- 1.在 PC 浏览器上登录微博，打开[minipublish 页面](https://weibo.com/minipublish)。`原因是因为这个页面内容少，请求数量比较少，更容易找 Cookie`
- 2.打开开发者工具`command + option + i`，选择 `Network` 栏
- 3.刷新页面，让开发者工具记录下网络请求，然后如图所示，选择最上面名为`minipublish`的请求
- 4.然后在右侧的 `Headers` 栏目下，找到如图红框里选中的内容即为需要的 Cookie 内容。`注意是 Cookie:` 后面的内容哦。
- 5.将此内容复制到 uPic 配置界面的 `Cookie` 输入框中

## ⚖️ 两种模式优缺点比较

- `用户名、密码模式`: 会自动通过配置好的用户名、密码进行调用登录接口获取 Cookie 再进行上传操作。`缺点：上传速度慢，因为需要多走一道网络请求`
- `Cookie 模式`: 上传速度快。`缺点：需要手动获取 Cookie，不动技术的人操作起来有点复杂`

> 大家自己选择喜欢的方式吧
