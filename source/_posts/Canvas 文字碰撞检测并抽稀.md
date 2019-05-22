---
title: Canvas 文字碰撞检测并抽稀
tags:
  - Canvas
  - Web
categories: "Notes"
date: 2019/05/10
thumbnail: //s2.svend.cc/thumb/map.svg
toc: true
widgets:
  - type: toc
    position: left
  - type: recent_posts
    position: left
sidebar:
  left:
    sticky: true
  right:
    sticky: true
---

#### 需求背景

一般在做地图相关的需求是才会用到文字抽稀，我也是在为公司的地图引擎实现一个功能时才实现了该方法，在这里将其简化了，就在普通的 Canvas 上进行操作，并没有引入地图概念

<!-- more -->

#### 效果

![text](https://s2.svend.cc/post/text-collision/collision.gif)

#### 碰撞检测

##### 计算文字在 canvas 中所占据的范围

```js
// 计算文字所需的宽度
var p = {
  x: 10,
  y: 10,
  name: "测试文字"
};
var measure = ctx.measureText(p.name);
// 求出文字在 canvas 画板中占据的最大 y 坐标
var maxX = measure.width + p.x;
// 求出文字在 canvas 画板中占据的最大 y 坐标
// canvas 只能计算文字的宽度，并不能计算出文字的高度。所以就利用文字的宽度除以文字个数计算个大概
var maxY = measure.width / p.name.length + p.y;

var min = { x: p.x, y: p.y };
var max = { x: maxX, y: maxY };
// bounds 为该文字在 canvas 中所占据的范围。
// 在取点位坐标作为最小范围时，textAlign、textBaseline 按照以下方式设置会比较准确。
// 如设置在不同的位置展示，范围最大、最小点也需进行调整
// ctx.textAlign = "left";
// ctx.textBaseline = "top";
var bounds = new Bounds(min, max);
```

Bounds 范围对象

```js
/**
 * 定义范围对象
 */
function Bounds(min, max) {
  this.min = min;
  this.max = max;
}

/**
 * 判断范围是否与另外一个范围有交集
 */
Bounds.prototype.intersects = function(bounds) {
  var min = this.min,
    max = this.max,
    min2 = bounds.min,
    max2 = bounds.max,
    xIntersects = max2.x >= min.x && min2.x <= max.x,
    yIntersects = max2.y >= min.y && min2.y <= max.y;

  return xIntersects && yIntersects;
};
```

##### 检测

```js
// 每次绘制之前先与已绘制的文字进行范围交叉检测
// 如发现有交叉，则放弃绘制当前文字，否则绘制并存入已绘制文字列表
for (var index in _textBounds) {
  // 循环所有已绘制的文字范围，检测是否和当前文字范围有交集，如果有交集说明会碰撞，则跳过该文字
  var pointBounds = _textBounds[index];
  if (pointBounds.intersects(bounds)) {
    return;
  }
}

_textBounds.push(bounds);
ctx.fillStyle = "red";
ctx.textAlign = "left";
ctx.textBaseline = "top";
ctx.fillText(p.name, p.x, p.y);
```

#### 示例、代码地址

示例地址：[示例](https://svend.cc/demo/canvas/text-collision)
具体可查看完整代码： [Github 地址](https://github.com/gee1k/demo/blob/master/canvas/text-collision.html)
