---
title: CSS Hacks
tags:
  - CSS
  - Web
categories: Notes
date: 2019/04/16
thumbnail: //s2.svend.cc/thumb/static_assets.svg
toc: true
widgets:
  - type: toc
    position: left
  - type: recent_posts
    position: left
---

> CSS Hacks, 持续补充

<!-- more -->

### 解决 div 高度崩塌

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Testing</title>
    <style>
      .o {
        border: 1px solid #000;
      }
      /* 将 after 伪元素设置为块元素添加到元素最后，然后对其清除浮动 */
      .o:after {
        content: "";
        display: block;
        clear: both;
      }

      .i {
        width: 50px;
        height: 50px;
        background: red;
        float: left;
        clear: both;
      }
    </style>
  </head>
  <body>
    <div class="o">
      <div class="i"></div>
    </div>
  </body>
</html>
```

### CSS 禁止换行

```css
overflow: hidden; /* 超出隐藏 */
text-overflow: ellipsis; /* 文字省略号 */
word-break: keep-all; /* 禁止文字中断 */
white-space: nowrap; /* 空白不允许换行 */
```

<!-- more -->

### 使用 `vertical-align` 解决 `inline-block` 元素的基线问题

```css
display: inline-block;
vertical-align: top; /* 设置 vertical-align 的元素必须是内联元素 */
```

### 黑白图片

```css
img.desaturate {
  filter: grayscale(100%);
}
```

### 页面顶部阴影

```css
body:before {
  content: "";
  position: fixed;
  top: -10px;
  left: 0;
  width: 100%;
  height: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.8);
}
```

### 优化显示文本

```css
html {
  text-rendering: optimizeLegibility;
}
```

### 文本渐变

```html
<p class="gradient" data-text="文本渐变"></p>
```

```css
.gradient[data-text] {
  position: relative;
}
.gradient[data-text]::after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  color: red;
  -webkit-mask-image: -webkit-gradient(
    linear,
    0 bottom,
    100 bottom,
    from(#ff0000),
    to(rgba(0, 0, 255, 0))
  );
}
```

### 模糊文本

```css
.blur {
  color: transparent;
  text-shadow: 0 0 5px rgba(0, 0, 0, 0.5);
}
```

### 修改鼠标手势

- 以下是常用的：

  ```css
  cursor: pointer | wait | hand | text | move | not-allowed;
  ```

- 自定义图片：

  ```css
  cursor: url(cat.png), auto; /* 尽量在后面加上一般的手势，以防自定义URL找不到时出现问题 */
  ```

### currentColor

> `currentColor`: 标识当前的标签所继承的文字颜色

```html
<div class="out-text">
  鼠标来我这儿！
  <div class="inside-box"></div>
</div>
```

```css
.out-text {
  width: 50px;
  color: red;
}
.out-text:hover {
  color: green;
}
.inside-box {
  width: 50px;
  height: 50px;
  background-color: currentColor;
}
```

### 修改 Chrome 默认滚动条样式

```css
::-webkit-scrollbar-track {
  border-radius: 10px;
  background-color: transparent;
}

::-webkit-scrollbar {
  width: 0.25rem;
  height: 0.25rem;
  background-color: transparent;
}

::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: rgba(153, 153, 153, 0.9);
  display: none; /* 默认隐藏滚动条 */
}

*:hover::-webkit-scrollbar-thumb {
  display: block; /* 当鼠标进入标签时显示滚动条 */
}
```

### 设置图片的高度与宽度相等

_HTML:_

```html
<div class="box">
  <img src=".......">
</box>
```

_CSS:_

```CSS
/* box css*/
.box {
  position: relative;
  width: 300px;
}
.box:before {
  content: '';
  display: block;
  padding-top: 100%;
}

/* img */
.box img {
  position:  absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}
```
