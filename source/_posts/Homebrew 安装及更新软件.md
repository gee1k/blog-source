---
title: Homebrew 安装及更新软件
tags:
  - Mac
categories: "Notes"
date: 2019/04/18
---

## brew

- brew install 安装

- brew uninstall 卸载

- brew update 更新 homebrew

- brew upgrade 安装已更新软件

- brew cleanup 清理

  ```bash
  # 一键更新清理
  brew update && brew upgrade && brew cleanup
  ```

## brew cask

### 安装 cask

```bash
brew tap caskroom/cask
```

### 命令

- brew cask install 安装
- brew cask uninstall 卸载

> Brew 更新软件很简单 。但是 brew cask 就没这么简单了。
>
> 有难题，总会有人解决难题。https://github.com/buo/homebrew-cask-upgrade

### 安装 brew-cask-upgrade

```bash
brew tap buo/cask-upgrade
```

### 更新命令

更新所有过时应用：

```bash
brew cu
```

更新指定应用：

```bash
brew cu [CASK]
```
