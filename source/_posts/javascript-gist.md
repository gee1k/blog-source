---
title: JavaScript 实用 Gist
tags:
  - Javascript
  - Web
categories: Notes
date: 2019/04/15
thumbnail: //s2.svend.cc/thumb/JavaScript_Frameworks.svg
toc: true
widgets:
  - type: toc
    position: left
  - type: recent_posts
    position: left
abbrlink: 13416c90
---

> 一些 JavaScript 中使用的方法等... 持续更新

<!-- more -->

### 根据图片路径转换为 Base64

```js
/**
 * @param src 图片路径
 * @param callback 转换完成之后的图片base64
 * @param outputFormat 需要转换的图片格式，默认 'image/jpg'
 */
function imgPathToDataURL(src, callback, outputFormat) {
  var canvas = document.createElement("canvas");
  var ctx = canvas.getContext("2d");
  var img = new Image();
  img.crossOrigin = "Anonymous";
  img.onload = function() {
    canvas.height = img.height;
    canvas.width = img.width;
    ctx.drawImage(img, 0, 0);
    var dataURL = canvas.toDataURL(outputFormat || "image/jpg");
    callback.call(this, dataURL);
    canvas = null;
  };
  img.src = src;
}
```

### Base64 转 Blob

```js
/**
 * @param dataURL base64
 */
function dataURLtoBlob(dataURL) {
  var byteString;
  if (dataURL.split(",")[0].indexOf("base64") >= 0)
    byteString = atob(dataURL.split(",")[1]);
  else byteString = unescape(dataURL.split(",")[1]);

  var mimeString = dataURL
    .split(",")[0]
    .split(":")[1]
    .split(";")[0];

  var ia = new Uint8Array(byteString.length);
  for (var i = 0; i < byteString.length; i++) {
    ia[i] = byteString.charCodeAt(i);
  }

  return new Blob([ia], { type: mimeString });
}
```

### 统计字符串中各个字符出现的次数

```js
function repeatCount(str) {
  return str
    .split("")
    .reduce((pre, cur) => (pre[cur]++ || (pre[cur] = 1), pre), {});
}

var str = "abcdaabc";
var info = repeatCount(str);
console.log(info); // { a: 3, b: 2, c: 2, d: 1 }
```

<!-- more -->

### URL 参数转 key/value

```js
const fomartUrlParams = url =>
  url
    .match(/([^?=&]+)(=([^&]*))/g)
    .reduce(
      (a, v) => (
        (a[v.slice(0, v.indexOf("="))] = v.slice(v.indexOf("=") + 1)), a
      ),
      {}
    );
fomartUrlParams("https://svend.cc/?name=gee1k&gender=man"); // -> {name: "gee1k", gender: "man"}
```

### 格式化日期时间

```js
const parseTime = (date, fmt) => {
  var o = {
    "M+": date.getMonth() + 1, //月份
    "d+": date.getDate(), //日
    "h+": date.getHours(), //小时
    "m+": date.getMinutes(), //分
    "s+": date.getSeconds(), //秒
    S: date.getMilliseconds() //毫秒
  };
  if (/(y+)/.test(fmt))
    fmt = fmt.replace(
      RegExp.$1,
      (date.getFullYear() + "").substr(4 - RegExp.$1.length)
    );
  for (var k in o)
    if (new RegExp("(" + k + ")").test(fmt))
      fmt = fmt.replace(
        RegExp.$1,
        RegExp.$1.length == 1 ? o[k] : ("00" + o[k]).substr(("" + o[k]).length)
      );
  return fmt;
};

parseTime(new Date(), "yyyy-MM-dd");
parseTime(new Date(), "yyyy-MM-dd hh:mm:ss");
parseTime(new Date(), "hh:mm");
```

### 深度克隆

```js
const deepClone = source => {
  if (!source && typeof source !== "object") {
    throw new Error("error arguments", "shallowClone");
  }
  const targetObj = source.constructor === Array ? [] : {};
  for (const keys in source) {
    if (source.hasOwnProperty(keys)) {
      if (source[keys] && typeof source[keys] === "object") {
        targetObj[keys] = source[keys].constructor === Array ? [] : {};
        targetObj[keys] = deepClone(source[keys]);
      } else {
        targetObj[keys] = source[keys];
      }
    }
  }
  return targetObj;
};
deepClone({ a: "1", b: 2 });
```

### 阻止事件冒泡

```js
function stopBubble(event) {
  if (event && event.stopPropagation) {
    event.stopPropagation();
  } else {
    window.event.cancelBubble = true;
  }
}
```

### 防抖

```js
const debounce = (func, wait, immediate) => {
  let timeout, args, context, timestamp, result;

  const later = function() {
    // 据上一次触发时间间隔
    const last = +new Date() - timestamp;

    // 上次被包装函数被调用时间间隔last小于设定时间间隔wait
    if (last < wait && last > 0) {
      timeout = setTimeout(later, wait - last);
    } else {
      timeout = null;
      // 如果设定为immediate===true，因为开始边界已经调用过了此处无需调用
      if (!immediate) {
        result = func.apply(context, args);
        if (!timeout) context = args = null;
      }
    }
  };

  return function(...args) {
    context = this;
    timestamp = +new Date();
    const callNow = immediate && !timeout;
    // 如果延时不存在，重新设定延时
    if (!timeout) timeout = setTimeout(later, wait);
    if (callNow) {
      result = func.apply(context, args);
      context = args = null;
    }

    return result;
  };
};
```

> Demo:

```js
const a = () => {
  console.log("debounce");
};
const b = debounce(a, 1000);
setInterval(() => {
  b();
}, 50);
```

### 合并 Object

```js
const objectMerge = (target, ...source) => {
  if (typeof target !== "object") {
    target = {};
  }
  source.forEach(src => {
    for (const property in src) {
      if (src.hasOwnProperty(property)) {
        const srcProperty = src[property];
        if (typeof srcProperty === "object") {
          target[property] = objectMerge(target[property], srcProperty);
          continue;
        }
        target[property] = srcProperty;
      }
    }
  });
  return target;
};

objectMerge({ a: 1, b: 22 }, { a: 5, c: 3 }, { s: 234, b: 222, h: { a: 1 } }); // ->  "{"a":5,"b":222,"c":3,"s":234,"h":{"a":1}}"
```

### 数组去重

```js
const deleteDuplicate = arr => [...new Set(arr)];
deleteDuplicate([1, 2, 3, 4, 5, 1, 2, 3]); // -> [1, 2, 3, 4, 5]
```

### 数组平均数

```js
const average = arr => arr.reduce((pre, cur) => pre + cur, 0) / arr.length;
average([1, 2, 3]); // -> 2
```

### 大写每个单词的首字母【借鉴】

```js
const capitalizeEveryWord = str =>
  str.replace(/\b[a-z]/g, char => char.toUpperCase());
capitalizeEveryWord("hello world"); //  -> 'Hello World'
```

### 字符串首字母大写

```js
const capitalize = (str, lowerOther = false) =>
  str.slice(0, 1).toUpperCase() +
  (lowerOther ? str.slice(1).toLowerCase() : str.slice(1));
capitalize("helloWorld"); //  -> 'HelloWorld'
capitalize("helloWorld", true); //  -> 'Helloworld'
```

### 检查回文【借鉴】

```js
const palindrome = str => {
  const s = str.toLowerCase().replace(/[\W_]/g, "");
  return (
    s ===
    s
      .split("")
      .reverse()
      .join("")
  );
};
palindrome("abc cba"); // -> true
```

### 统计数组中值的出现次数【借鉴】

```js
const countOccurrences = (arr, value) =>
  arr.reduce((pre, cur) => (cur === value ? pre + 1 : pre + 0), 0);
countOccurrences([1, 1, 2, 1, 2, 3], 1); // -> 3
```

### 获取两个数组之间的差集【借鉴】

```js
const difference = (a, b) => {
  const s = new Set(b);
  return a.filter(x => !s.has(x));
};
difference([1, 2, 3], [1, 2]); //  -> [3]
```

### 斐波那契数组生成器【借鉴】

> 生成指定个数的斐波那契数组

```js
const fibonacci = n =>
  Array(n)
    .fill(0)
    .reduce(
      (pre, cur, i) => pre.concat(i > 1 ? pre[i - 1] + pre[i - 2] : i),
      []
    );
fibonacci(5); // -> [0,1,1,2,3]
```

### 用 Rnage 初始化数组【借鉴】

```js
const rangeArray = (end, start = 0) =>
  Array.apply(null, Array(end - start)).map((v, i) => i + start);
rangeArray(5); // -> [0,1,2,3,4]
```

### 范围内的随机整数【借鉴】

```js
const randomIntegerInRange = (min, max) =>
  Math.floor(Math.random() * (max - min + 1)) + min;
randomIntegerInRange(100, 150); // -> 143
```

### 范围内的随机数【借鉴】

```js
const randomInRange = (min, max) => Math.random() * (max - min) + min;
randomInRange(10, 20); // -> 12.27232719315272
```
