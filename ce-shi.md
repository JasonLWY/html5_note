# 深圳xyxyxy H5 1705班第6周笔试

###注意：==将答案写在答题卡上，答题卡的文件名一定是你的名字==

---

## 一. 选择题(每题2分, 共60分. 注意:从第26题开始为不定项选择题)

1. 在以下代码中, 哪些是局部变量? ( )

   ```javascript
   <script>
     var a = 3;
     if(a == 3){
         var b = 4;
     }
     for(var i = 0; i < 3; i++){
         var c = 10;
     }
     function foo(){
         var d = 20;
     }
     foo()
   </script>
   ```
   ---

   (A) b, c,d

   (B) a, b,c

   (C) b,i,c,d

   (D)d   

2. 以下声明函数的代码, 错误的是( )

   (A) `function foo(){ }`

   (B) `var foo = function(){ }`

   (C) `var foo = function(a){  }`

   (D)` var foo(){  }`

   ---

3. 以下哪个语句打印出来的结果是` true` ：( ) 

   (A) `alert("12" === 12);`
   (B) `alert(NaN === NaN);`
   (C) `alert(typeof null  === typeof(window));`
   (D) `alert([1,2,3] === [1,2,3]);`

   ---

4. 以下描述中错误的是：( ) 
   (A) `alert(typeof(99)) 显示的内容为：number`
   (B) `alert(typeof(null)) 显示的内容为：object`
   (C) `alert(typeof(undefined)) 显示的内容为：undefined`
   (D) `alert(typeof(function() {})) 显示的内容为：Function`

   ---

5. 有一个 HTML  页面，其源码如下，在 `FireFox ` 点击 “ 提交 ” 按钮，依次显示的内容，
   正确的是：( )

   ```javascript
   <body onclick="alert('body')">
     <div onclick="alert('div')">
         <button onclick="alert('button')">按钮</button>
     </div>
   </body>
   ```

   (A) `body，div，button，div，body`
   (B) `div, button, body`
   (C) `button，div，body`
   (D) 以上都不对

   ---

6. 执行下面的代码, 结果正确的是:( )

   ```javascript
   <script>
     var a = 10;

     function foo(){
         console.log(a);
         var a = 20;
         console.log(a);
     }

     console.log(a);
     foo()
   </script>
   ```

   (A) `10, 10, 20`

   (B) `10, undefined, 20`

   (C) `20, 20, 20`

   (D) 以上都不对

   ---

7. 看下面的代码, 正确的信息显示顺序是: ()

   ```html
   <!DOCTYPE html>
   <script>
   var show = function (){
       alert("show_function")
   }
   alert("script")
   </script>
   <html lang="en">
   <head>
   <meta charset="UTF-8">
   <title>Title</title>
   </head>
   <body onload="alert('onload')">
   <script>
   alert("in_body")
   </script>
   </body>
   </html>
   <script>
   show();
   </script>
   ```

   (A) `show_function，script，onload，in_body`
   (B) `script，onload，in_body，show_function`
   (C)` script，in_body，show_function，onload`
   (D)` script，in_body，onload，show_function`

   ---

8. 下列哪个能产生一个`[3, 7]`的随机整数(`包括3也包括7`).

   (A) `Math.random()*4+3`

   (B) `parseInt(Math.random()) * 5 + 3`

   (B) `parseInt(Math.random() * 5) + 3`

   (D) B和C都对

   ---

9. 有数组 `var arr = [1, 2, 3]`, 下面哪个不可以修改数组`arr`的长度( ):

  (A) `arr.slice(1, 2)`

  (B) `arr.length = 100`

  (C) `arr.splice(0, 1)`

  (D) `arr[3] = 4`

  ---

10. 以下关于 `Array`  数组对象的说法正确的是（ ）
  (A) 对数组里数据的排序可以用 `sort` 函数，如果排序效果非预期，可以给` sort `函数加一个排序函数的参数       
  (B) `reverse` 用于对数组数据的正序排列       
  (C) 向数组的最后位置加一个新元素，可以用 `pop` 方法      
  (D) `unshift` 方法用于向数组删除第一个元素        

  ---

11. 关于正则表达式声明 6  位数字的邮编 ， 以下代码正确的是 （ ）
   (A) `var reg = /\d6/`;
   (B) `var reg = \^\d{6}^\`;
   (C) `var reg = /^\d{6}$/`;
   (D) `var reg = new RegExp("^\d{6}^")`;

   ---

12. 看以下 JavaScript  程序

    ```javascript
      var x=prompt("请输入 1-5 的数字！");
      switch (x)
        case "1":alert("one");
        case "2":alert"two");
        case "3":alert("three");
        case "4":alert("four");
        case "5":alert("five");
        default:alert("none");
    ```

    运行以上程序，在提示对话框中输入“4”，依次弹出的对话框将输出:( )

    (A) `four,none`

    (B) `four,five,none`

    (C) `five`

    (D) `five,none`

    ---

13. 分析下面的 JavaScript  代码段, 输出结果是( )

    ```javascript
    var a=new Array(2,3,4,5,6);
    var sum=0;
    for(var i=1; i < a.length; i++)
    	sum +=a[i];
    console.log(sum);
    ```

    (A) 20
    (B) 18
    (C) 14
    (D) 12

    ---

14. 下面的代码输出是：

    ```javascript
    console.log("" || 100);  
    console.log("0" || true); 
    console.log(null && 100); 
    console.log("0" && true); 
    ```

    (A) `100  0  null  true`

    (B) `100  true  100   0`

    (C) `""   true   null true`

    (D) `100  0   100   true`

    ---

15. 分析下面的 JavaScript  代码段, 输出的结果是( )

    ```javascript
    var a=15.69;
    console.log(Math.floor(a));
    ```

    (A) 15
    (B) 16
    (C) 15.5
    (D) 15.4

    ---

16. 如果函数内没有`return`语句, 则调用这个函数真正返回:（ ）。

    (A) `null`

    (B) `None`

    (C) `undefined`

    (D) `-1`

    ---

17. 下列结果正确的是()

    (A) `"300" - 200` 结果是:`100`

    (B)  `"300" - 200` 结果是:报错

    (C)  `"300" + 200` 结果是:报错

    (D) 以上都对

    ---

18. 在JavaScript中, `alert(null==undefined)`的输出结果是:

    (A) `null`

    (B) `undefined`

    (C) `true`

    (D) `false`

    ---

19. 看下面的代码

    ```javascript
    var a =  [10, 20, 30];
    a.splice(1, 2, 3, 4);
    console.log(a[1])
    ```

    (A) 最后一行代码输出: `10`

    (B) 最后一行代码输出: `20`

    (C) 最后一行代码输出:`3`

    (D) 最后一行代码输出:`4`

    ---

20. 看下面的代码片段, 找到正确的输出顺序

    ```javascript
    console.log("1");
    setTimeout(function(){
    	console.log("2");
    }, 0);
    console.log("3")
    ```

    (A) `1 2 3`

    (B) `2 1 3`

    (C) `3 1 2`

    (D) `1 3 2`

    ---

21. 看如下代码片段, 当下面的代码段执行结束之后, 请问`a.length` 的值是多少?

    ```javascript
    var a = [];
    a[0] = 1;
    a[3] = 4;
    a[6] = 7;
    console.log(a[8]);
    ```

    (A) 报错

    (B) `7`

    (C) `8`

    (D) `9`

    ---

22. 在javascript中, 用于阻止事件的默认操作的方法是:
    (A) `stopDefault()`

    (B) `preventDefault()`

    (C) `stopPropagation()`

    (D) `preventPropagation()`

    ---

23. 给父节点追加子节点的方法是: (  )

    (A) `appendBefore()`  

    (B) `appendChild()`   

    (C) `insertBefore()`  

    (D) `insertChild()`

    ---

24. 下面哪个不是`节点Node`的属性(      )

    (A) `nodeName` 

    (B) `nodeValue`

    (C) `nodeType`

    (D) `nodeXML`

    ---

25. 分析下面的代码, 输出结果是: ()

    ```javascript
    var s1=parseInt(“110xyxyxy”); 
    document.write(s1); 
    ```

    (A) `NaN` 

    (B) `101中学`

    (C) `101`   

    (D) `出现脚本错误`

    ---

26. 以下比较, 结果是`true`的是: ( ) (不定项选择题)

    (A) `[0] == [0]`

    (B) `[0] == "0"`

    (C) `[] == 0`

    (D) `1 == "1"`

    ---

27. 在正则表达式中,(   )符号表示获取至少一个符合的字符.

    (A) `*`  

    (B) `+`  

    (C) `?`   

    (D) `{1,}`

    ---

28. 下面`document`对象中的(  )方法返回的只是一个元素对象，而不是元素集合

    (A) `getElementById()`  

    (B) `getElementsByClassName()` 

    (C) `getElementsByName()` 

    (D) `getElementsByTagName()`

    ---

29. 下面js代码运行的结果是: ( )

    ```javascript
    var a = 2017 < 2016 || typeof(2017 + "0")
    console.log(a);
    ```

    (A) `true`

    (B) `string`

    (C) `String`

    (D) `number`

    ---

30. 下面的代码输出结果是:( )

    ```javascript
    var a = [10, 20];
    var b = 100;
    function foo(a, b){
        a.unshift(30);
        b = 200;
    }

    foo(a, b);
    console.log(a[0]);
    console.log(b);
    ```

    (A) `30 100`
    (B) `10 100`
    (C) `20 200`
    (D) `30 200`

    ---


## 二. 问答题(40分)

1. 已知有如下标签, 至少写出 5 中找到`p`元素的方式: (5分)

   ```html
   <div id="box">
     <p id="conetnt" class="p1">
       
     </p>
   </div>
   ```

   ---

2. 写出匹配`2000-01-01到2016-12-31`的正则表达式。(5分)

   ---

3. 写出你知道的javascript的数据类型.(5分)

   ---

4. 写出`innerHTML和innerText`的区别(5分)

   ---

5. 已知如下代`HTML`结构:(5分)

   ```html
   <ul>
     <p>
       文本内容
     </p>
   </ul>
   ```

   请使用`javascript`代码, 把上面的结构变成下面的结构.

   ```html
   <ul>
     <li>
       <p>
         文本内容
     	</p>
     </li>
   </ul>
   ```

   ---

6. 实现下面的函数, 能够打乱数组的元素, 需要打乱的数组已经通过参数传递进去了:(假设数组中的元素都是数字)(5分)

   ```javascript
   function upset(arr){
       // TODO:
   }
   ```

   ---

7. 实现下面的函数, 能够去除数组中的重复元素,, 需要去重的数组已经通过参数传递进去了:(假设数组中的元素都是数字)(10分)

   ```javascript
   function removeHeavy(arr){
       //TODO:
   }
   ```

   ​