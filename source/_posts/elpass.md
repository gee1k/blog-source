---
title: Elpass - macOS & iOS 上的密码管理新选择
tags:
  - CSS
  - Web
categories: Essays
date: 2019/12/17
thumbnail: https://cdn.jsdelivr.net/gh/gee1k/oss@master/blog/2019/12/17/elpass-poster.png
toc: true
widgets:
  - type: toc
    position: left
sidebar:
  left:
    sticky: true
  right:
    sticky: true
---

前几天 `iOS&macOS` 上的知名网络调试工具 `Surge` 的作者发布了一款新的密码管理工具- `Elpass` ，我也第一时间下载下来体验了一把。之前一直使用的 `1Password` 这个大名鼎鼎的软件， `1Password` 的便捷性不必多说，功能也是很完善，但是时代与时俱进，也正是 `1Password` 的功能太完善，造成了现在的臃肿， `iOS` 上的密码填充常常无法自动调用指纹或者面容来解锁，总是要手动点击一下，非常的麻烦，而 `Elpass` 在安全性选择上解决了这个问题。

<!-- more -->

# 界面

![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/blog/2019/12/17/elpass-1.png)
![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/blog/2019/12/17/elpass-2.png)

界面没有特别新奇的特点，从上到下依次为 All Items、Favorites、Logins、Bank Cards、Identifications、Secure Notes、Passwords、Archived，这些分类已经可以满足记录所需了，比 1Password 少了两个分类，信用卡（Elpass 已经整合在 Bank Cards 中）和软件许可（这一分类看 Twitter 上作者的回复认为没有必要，大概率不会增加，不过未来也说不准）

最底下还有一个 Smart Items 智能列表，High Security Level 不太清楚是干什么的，OTP Configured 分类可以看到已经添加一次性密码的条目。

密码是默认不可见的，1Password 需要在下拉菜单点击显示，Elpass 只需要在密码右侧点击 Reveal 就可以显示出来，方便快捷

Elpass 的删除规则也非常的贴切，1Password 中我们删除是直接放到了废纸篓里，这个废纸篓如果我们不主动清空他是永远不会被删除的，而 Elpass 则直接叫做归档，我们在归档里删除才是真正的删除。

新建条目的时候设置密码也没有 1Password 那样繁琐的设置，1Password 设置密码的时候设置好长度还要设置数字、符号需要几位。

Elpass 选择好密码需要包含的字符就可以了，不满意可以点击密码右侧的刷新按钮一直刷新，直到刷新到你自己满意的密码（其实没必要刷新，毕竟密码都是没有任何规则的）

# 安全性

![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/blog/2019/12/17/elpass-3.png)

Elpass 密码分三个等级，可以让我们灵活的自主选择什么时候需要密码，什么时候不需要密码。

Elpass 的加密模块已经开源，有兴趣的可以[点击跳转](https://github.com/surge-networks/Elpass-Core)看一下代码。

目前只支持 iCloud 和 Dropbox 两个网盘的同步，还不支持 Wi-Fi 同步，对于不信任网盘的朋友可能会比较难受。

# 方便

Elpass 开机解锁功能会把主密码保存到系统的 keychain 中，省去繁琐的主密码输入阶段。如果我们勾选上 Require Touch ID for auto unlock 这个功能，则会弹出指纹解锁，只有指纹通过才能解开密码库，当然你的电脑需要有指纹功能。

![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/blog/2019/12/17/elpass-4.png)

Elpass 已经有了对应 Safari、Chrome、Firefox 的插件，方便网页的自动填充（不会自动提交，方便账号修改），当我们登录一些有二次验证密码的网站的时候，Eplass 也会同时弹出一个二次密码的框，并有 copy 和 auto type 两个功能，

点击 auto type Eplass 会自动把数字填入目标框，如果目标框是不支持自动填入或者粘贴的，也可以方便的手动对照输入，这一点比 1Password 方便，1Password 只是把二次密码放进了剪贴板，后续操作则不在管。

# 原生 App 填充（Mac App Store 版本不支持

![](https://cdn.jsdelivr.net/gh/gee1k/oss@master/blog/2019/12/17/elpass-5.png)

这个功能算是 Elpass 的大亮点了，不管我们用 1Password 还是系统的 keychain，这些密码管理在 native 的 app 上都是不会自动填充的。

Eplass 会在响应对象为密码框的时候显示一个已保存对应 app 的所有密码备选，这个识别内容是通过 App 的 Bunder 标识符来识别的，下面我们来讲一讲怎么获取这个标识符。

方法一：

在 Elpass 的官网上提供了一个方法

 `osascript -e 'id of app "APPNAME"'` 我们把 `APPNAME` 替换成我们想要获取的 App 的名字，例如我们如果想要获取 QQ 的标识符只需要把命令行改成`osascript -e 'id of app "QQ"'` 会得到一个 `com.tencent.qq` 的 url，我们反转一下就是 `qq.[tencent.com](http://tencent.com)`，删掉 `qq.`，把 `tencent.com` 填写到 Elpass 对应 QQ 的密码项的 `Domains` 中，就可以识别了。（如果不行，重启一下 Elpass 或者目标 App）

方法二：

 `mdls -name kMDItemCFBundleIdentifier -r app`把最后的 app 替换成目标 app 的路径，可以直接拖进终端完整的路径，例如 `mdls -name kMDItemCFBundleIdentifier -r /Applications/iTunes.app` 回车，会得到一个 com.apple.iTunes ，之后和方法一一样。

方法三：

这个方法最简单，最高效，也是最搞笑的，需要利用到 1Password，免费版不知道可不可以，我是 7 代买断版本，1Password 在之前的一个版本中也增加了识别目标 App，但是并没有 Elpass 那么方便的自动填充，而是在 1Password 的窗口中显示出来，方便复制粘贴。

而我发现如果我们打开目标 app，点击 1Password 的填充快捷键，1Password 会显示目标的密码项，如果没有就是空的，这时候我们看 1Password 的搜索框会发现出现了一个网址，这个网址就是方法一和方法二得到并且反转完成的结果，我们直接复制到 Elpass 的 domains 中就搞定了，很骚气的方法。

# 目前的不足

1. Elpass 目前不支持文件保存（这一点还是非常非常需要的
2. 订阅的单一性，目前只支持年订阅（$19.99/year
3. 还没有类似 1Password 的标签功能
4. Windows&Android 两端无法使用（作者的意思会出一个折中的替代品

