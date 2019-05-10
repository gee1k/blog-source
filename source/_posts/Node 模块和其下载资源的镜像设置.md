---
title: Node 模块和其下载资源的镜像设置
tags:
  - Node
  - Npm
categories: "Notes"
date: 2018/10/01
---

以前安装 `electron` 时总是失败，然后就在`淘宝镜像`上下载好相应版本的文件放到用户目录来解决问题。

后来研究发现 `npm` 不仅可以设置 `node.js` 模块仓库的代理， 同样可以设置像 [electron](https://github.com/electron/electron)、[phantomjs](https://github.com/Medium/phantomjs#deciding-where-to-get-phantomjs)、 [node-sass](https://github.com/sass/node-sass#binary-configuration-parameters) 等模块的镜像代理

<!-- more -->

## 一、设置淘宝镜像 （共三种方法）

### 1.环境变量

Unix：

```shell
# electron
export ELECTRON_MIRROR=https://npm.taobao.org/mirrors/electron/
# phantomjs
export PHANTOMJS_CDNURL=https://npm.taobao.org/mirrors/phantomjs/
# node-sass
export SASS_BINARY_SITE=https://npm.taobao.org/mirrors/node-sass/
```

Windows：

```cmd
# electron
set ELECTRON_MIRROR=https://npm.taobao.org/mirrors/electron/
# phantomjs
set PHANTOMJS_CDNURL=https://npm.taobao.org/mirrors/phantomjs/
# node-sass
set SASS_BINARY_SITE=https://npm.taobao.org/mirrors/node-sass/
```

### 2.`npm` 执行参数

```shell

# electron
npm install electron --electron-mirror=https://npm.taobao.org/mirrors/electron/
# phantomjs
npm install phantomjs --phantomjs_cdnurl=https://npm.taobao.org/mirrors/phantomjs/
# node-sass
npm install node-sass --sass-binary-site=https://npm.taobao.org/mirrors/node-sass/
```

### 3.使用本地（项目根目录）或全局（用户目录）[.npmrc](https://docs.npmjs.com/misc/config) 配置

```

registry=https://registry.npm.taobao.org
electron_mirror=https://npm.taobao.org/mirrors/electron/
sass_binary_site=https://npm.taobao.org/mirrors/node-sass/
phantomjs_cdnurl=https://npm.taobao.org/mirrors/phantomjs/
```

## 二、使用代理

除了使用代理来解决，更暴力直接的方法就是使用梯子了。
确保你要安装的模块仓库地址在代理 PAC 列表中或直接使用全局代理。npm 好像只支持 HTTP 代理

```shell

# 设置代理
npm config set proxy http://127.0.0.1:1085
# 安装模块
npm i --save-dev electron
# 删除代理
npm config delete proxy
```

> 推荐使用 `yarn`，速度会快很多
