JS 最强大的一方面就是它能极其轻易地处理异步编程。作为因互联网而生的语言， JS 从一开始就必须能够响应点击或按键之类的用户交互行为。 Node.js 通过使用回调函数来代替事件，进一步推动了 JS 中的异步编程。随着越来越多的程序开始使用异步编程，事件与回调函数已不足以支持开发者的所有需求。 Promise 正是为了解决这方面的问题。
Promise 是异步编程的另一种选择，它的工作方式类似于在其他语言中进行延迟并在将来执行作业。一个 Promise 指定一些稍后要执行的代码（就像事件与回调函数一样），并且也明确标示了作业的代码是否执行成功。你能以成功处理或失败处理为基准，将 Promise 串联在一起，让代码更易理解、更易调试。
不过为了更好理解 Promise 是如何工作的，重要的是理解建立它所依据的一些基本概念。

# 异步编程的背景

JS 引擎建立在单线程事件循环的概念上。单线程（ Single-threaded ）意味着同一时刻只能执行一段代码，与 Java 或 C++ 这种允许同时执行多段不同代码的多线程语言形成了反差。

## 事件模型

```javascript
let button = document.getElementById("my-btn");
button.onclick = function(event) {
    console.log("Clicked");
};
```

## 回调模式

```javascript
readFile("example.txt", function(err, contents) {
    if (err) {
        throw err;
    }

    console.log(contents);
});
console.log("Hi!");
```
这种模式运作得相当好，但当嵌套过多回调函数时，你可能会迅速察觉陷入了回调地狱（ callback hell ），就像这样：

```javascript
method1(function(err, result) {

    if (err) {
        throw err;
    }

    method2(function(err, result) {

        if (err) {
            throw err;
        }

        method3(function(err, result) {

            if (err) {
                throw err;
            }

            method4(function(err, result) {

                if (err) {
                    throw err;
                }

                method5(result);
            });

        });

    });

});
```

---
# Promise基础

Promise 是为异步操作的结果所准备的占位符。函数可以返回一个 Promise，而不必订阅一个事件或向函数传递一个回调参数，就像这样：

```javascript
// readFile 承诺会在将来某个时间点完成
let promise = readFile("example.txt");
```

在此代码中， readFile() 实际上并未立即开始读取文件，这将会在稍后发生。此函数会返回一个 Promise 对象以表示异步读取操作，因此你可以在将来再操作它。你能对结果进行操作的确切时刻，完全取决于 Promise 的生命周期是如何进行的。

---

# Promise生命周期

每个 Promise 都会经历一个短暂的生命周期，初始为`进行态（ pending state）`，这表示异步操作尚未结束。一个进行中的 Promise 也被认为是`未处理的（ unsettled ）`。上个例子中的 Promise 在 `readFile()` 函数返回它的时候就是处在进行态。一旦异步操作结束， Promise 就会被认为是已处理的`（ settled ）`，并进入两种可能状态之一：

- 已完成（ `fulfilled` ）： Promise 的异步操作已成功结束；
- 已拒绝（ `rejected` ）： Promise 的异步操作未成功结束，可能是一个错误，或由其他原因导致。

内部的 [[PromiseState]] 属性会被设置为` "pending" 、 "fulfilled" 或 "rejected" `，以反映 Promise 的状态。该属性并未在 Promise 对象上被暴露出来，因此你无法以编程方式判断 Promise 到底处于哪种状态。不过你可以使用` then()` 方法在 Promise 的状态改变时执行一些特定操作。

## `then()`方法

`then()` 方法在所有的 Promise 上都存在，并且接受两个参数。

第一个参数是 Promise 被完成时要调用的函数，与异步操作关联的任何附加数据都会被传入这个完成函数。

第二个参数则是 Promise 被拒绝时要调用的函数，与完成函数相似，拒绝函数会被传入与拒绝相关联的任何附加数据。

> 用这种方式实现 then() 方法的任何对象都被称为一个 thenable 。所有的 Promise 都是 thenable ，反之则未必成立。

传递给`then()`方法的两个参数都是可选的, 我们可以给出任意的组合.

```javascript
let promise = readFile("example.txt");

promise.then(function(contents) {
    // 完成
    console.log(contents);
}, function(err) {
    // 拒绝
    console.error(err.message);
});

promise.then(function(contents) {
    // 完成
    console.log(contents);
});

promise.then(null, function(err) {
    // 拒绝
    console.error(err.message);
});
```

## `catch()`方法

Promis 也具有一个 catch() 方法，其行为等同于只传递拒绝处理函数给 then() 。例如，以下的 catch() 与 then() 调用是功能等效的。

```javascript
promise.catch(function(err) {
    // 拒绝
    console.error(err.message);
});

// 等同于：

promise.then(null, function(err) {
    // 拒绝
    console.error(err.message);
});
```

## Node中读取文件的实现

```javascript
const fs = require("fs");
const readFile = path =>{
    return new Promise(function (resolve, reject){
        fs.readFile(path, "utf-8", function (err, data){
            if (err){
                reject(err);
                return;
            }
            resolve(data);
        })
    })
};

let promise = readFile("promise_demo.js");
promise.then(function (data){
    console.log(data);
}).catch(function (err){
    console.log("发生了错误");
})
```

要记住执行器会在 readFile() 被调用时立即运行。当 resolve() 或 reject() 在执行器内部被调用时，一个作业被添加到作业队列中，以便处理这个 Promise 。这被称为作业调度（ job scheduling ），若你曾用过 setTimeout() 或 setInterval() 函数，那么应该已经熟悉这种方式。在作业调度中，你添加新作业到队列中是表示：“不要立刻执行这个作业，但要在稍后执行它”。例如， setTimeout() 函数能让你指定一个延迟时间，延迟之后作业才会被添加到队列：

---


# 创建已处理的Promise

基于 Promise 执行器行为的动态本质， Promise 构造器就是创建未处理的 Promise 的最好方式。但若你想让一个 Promise 代表一个已知的值，那么安排一个单纯传值给 resolve() 函数的作业并没有意义。相反，有两种方法可使用指定值来创建已处理的 Promise 。







































