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

# Promise生命周期

每个 Promise 都会经历一个短暂的生命周期，初始为`进行态（ pending state）`，这表示异步操作尚未结束。一个进行中的 Promise 也被认为是`未处理的（ unsettled ）`。上个例子中的 Promise 在 `readFile()` 函数返回它的时候就是处在进行态。一旦异步操作结束， Promise 就会被认为是已处理的`（ settled ）`，并进入两种可能状态之一：

- 已完成（ `fulfilled` ）： Promise 的异步操作已成功结束；
- 已拒绝（ `rejected` ）： Promise 的异步操作未成功结束，可能是一个错误，或由其他原因导致。






































