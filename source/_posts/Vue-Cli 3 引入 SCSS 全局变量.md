---
title: Vue-Cli 3 引入 SCSS 全局变量
tags:
  - Web
  - Vue
categories: "Notes"
date: 2019/03/20
thumbnail: //s2.svend.cc/thumb/coding.svg
toc: true
widgets:
  - type: toc
    position: left
  - type: recent_posts
    position: left
---

## 首先创建一个全局变量文件 `global.scss`

<!-- more -->

```scss
$theme-color: #efefef;
```

## 编辑`vue.config.js`

```js
module.exports = {
  // ...
  css: {
    loaderOptions: {
      sass: {
        // 根据自己样式文件的位置调整
        data: `@import "@/styles/global.scss";`
      }
    }
  }
};
```

现在就可以在任意地方使用`global.scss`中定义的变量了

```vue
<template>
  <div class="box"></div>
</template>
<script>
export default {
  data() {
    return {};
  }
};
</script>
<style lang="scss">
.box {
  background-color: $theme-color;
}
</style>
```
