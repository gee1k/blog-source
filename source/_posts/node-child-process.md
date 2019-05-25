---
title: Node.js 多进程处理CPU密集任务
tags:
  - Node.js
categories: Notes
date: 2019/05/26
thumbnail: //s2.svend.cc/thumb/in_progress.svg
toc: true
widgets:
  - type: toc
    position: left
  - type: recent_posts
    position: right
sidebar:
  left:
    sticky: true
  right:
    sticky: true
---

## Node.js 多进程

大家都知道 Node.js 性能很高，是以异步事件驱动、非阻塞 I/O 而被广泛使用。但缺点也很明显，由于 Node.js 是单线程程序，如果长时间运算，会导致 CPU 不能及时释放,所以并不适合 CPU 密集型应用。

<!-- more -->

当然，也不是没有办法解决这个问题。虽然 Node.js 不支持多线程，但是可创建多子进程来执行任务。
Node.js 提供了 `child_process` 和 `cluster` 两个模块可用于创建多子进程

下面我们就分别使用单线程和多进程来模拟查找大量斐波那契数进行 CPU 密集测试

以下代码是查找 500 次位置为 35 的斐波那契数(方便测试，定了一个时间不需要太长也不会太短的位置)

## 单线程处理

### 代码：`single.js`

```js
function fibonacci(n) {
  if (n == 0 || n == 1) {
    return n;
  } else {
    return fibonacci(n - 1) + fibonacci(n - 2);
  }
}

let startTime = Date.now();
let totalCount = 500;
let completedCount = 0;
let n = 35;

for (let i = 0; i < totalCount; i++) {
  fibonacci(n);
  completedCount++;
  console.log(`process: ${completedCount}/${totalCount}`);
}
console.log("👏 👏 👏 👏 👏 👏 👏 👏 👏 👏");
console.info(`任务完成，用时: ${Date.now() - startTime}ms`);
console.log("👏 👏 👏 👏 👏 👏 👏 👏 👏 👏");
```

执行`node single.js` 查看结果

在我的电脑上显示结果为`44611ms`(电脑配置不同也会有差异)。

```js
...
process: 500/500
👏 👏 👏 👏 👏 👏 👏 👏 👏 👏
任务完成，用时: 44611ms
👏 👏 👏 👏 👏 👏 👏 👏 👏 👏
```

查找 500 次需要 44 秒，太慢了。可想而知如果位置更大，数量更多...

那我们来尝试用多进程试试 ⬇️

## 多进程

> 采用 `cluster` 模块，`Master-Worker` 模式来测试
> 共 3 个 js，分别为主线程代码：`master.js`、子进程代码：`worker.js`、入口代码：`cluster.js`(入口可无需单独写一个 js、这里是为了看起来更清楚一些)

### 主线程代码：`master.js`

```js
const cluster = require("cluster");
const numCPUs = require("os").cpus().length;

// 设置子进程执行程序
cluster.setupMaster({
  exec: "./worker.js",
  slient: true
});

function run() {
  // 记录开始时间
  const startTime = Date.now();
  // 总数
  const totalCount = 500;
  // 当前已处理任务数
  let completedCount = 0;
  // 任务生成器
  const fbGenerator = FbGenerator(totalCount);

  if (cluster.isMaster) {
    cluster.on("fork", function(worker) {
      console.log(`[master] : fork worker ${worker.id}`);
    });
    cluster.on("exit", function(worker, code, signal) {
      console.log(`[master] : worker ${worker.id} died`);
    });

    for (let i = 0; i < numCPUs; i++) {
      const worker = cluster.fork();

      // 接收子进程数据
      worker.on("message", function(msg) {
        // 完成一个，记录并打印进度
        completedCount++;
        console.log(`process: ${completedCount}/${totalCount}`);

        nextTask(this);
      });

      nextTask(worker);
    }
  } else {
    process.on("message", function(msg) {
      console.log(msg);
    });
  }

  /**
   * 继续下一个任务
   *
   * @param {ChildProcess} worker 子进程对象，将在此进程上执行本次任务
   */
  function nextTask(worker) {
    // 获取下一个参数
    const data = fbGenerator.next();
    // 判断是否已经完成，如果完成则调用完成函数，结束程序
    if (data.done) {
      done();
      return;
    }
    // 否则继续任务
    // 向子进程发送数据
    worker.send(data.value);
  }

  /**
   * 完成，当所有任务完成时调用该函数以结束程序
   */
  function done() {
    if (completedCount >= totalCount) {
      cluster.disconnect();
      console.log("👏 👏 👏 👏 👏 👏 👏 👏 👏 👏");
      console.info(`任务完成，用时: ${Date.now() - startTime}ms`);
      console.log("👏 👏 👏 👏 👏 👏 👏 👏 👏 👏");
    }
  }
}

/**
 * 生成器
 */
function* FbGenerator(count) {
  var n = 35;
  for (var i = 0; i < count; i++) {
    yield n;
  }
  return;
}

module.exports = {
  run
};
```

> 1.这里是根据当前电脑的逻辑 CPU 核数来创建子进程的，不同电脑数量也会不一样，我的 CPU 是 6 个物理核数，由于支持超线程处理，所以逻辑核数是 12，故会创建出 12 个子进程
>
> 2.主线程与子进程之间通信是通过`send`方法来发送数据，监听`message`事件来接收数据
>
> 3.不知道大家有没有注意到我这里使用了 ES6 的 Generator 生成器来模拟生成每次需要查找的斐波那契数位置(虽然是写死的 😂，为了和上面的单线程保证统一)。这么做是为了不让所有任务一次性扔出去，因为就算扔出去也会被阻塞，还不如放在程序端就给控制住，完成一个，放一个。

### 子进程代码：`worker.js`

```js
function fibonacci(n) {
  if (n == 0 || n == 1) {
    return n;
  } else {
    return fibonacci(n - 1) + fibonacci(n - 2);
  }
}

// 接收主线程发送过来的任务，并开始查找斐波那契数
process.on("message", n => {
  var res = fibonacci(n);
  // 查找结束后通知主线程，以便主线程再度进行任务分配
  process.send(res);
});
```

### 入口代码：`cluster.js`

```js
// 引入主线程js，并执行暴露出来的run方法
const master = require("./master");
master.run();
```

执行`node cluster.js` 查看结果

在我的电脑上显示结果为`10724ms`(电脑配置不同也会有差异)。

```js
process: 500/500
👏 👏 👏 👏 👏 👏 👏 👏 👏 👏
任务完成，用时: 10724ms
👏 👏 👏 👏 👏 👏 👏 👏 👏 👏
```

## 结果

进过上面两种方式的对比，结果很明显，多进程处理速度是单线程处理速度的 4 倍多。而且有条件的情况下，如果电脑 CPU 足够，进程数更多，那么速度也会更快。

如果有更好的方案或别的语言能处理你的需求那就更好，谁让 Node.js 天生就不适合 CPU 密集型应用呢。。
