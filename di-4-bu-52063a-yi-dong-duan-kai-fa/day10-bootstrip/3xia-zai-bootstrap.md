# 下载

## 直接下载生成版本

Bootstrap （当前版本 v3.3.7）提供以下几种方式帮你快速上手，每一种方式针对具有不同技能等级的开发者和不同的使用场景。

为了简单起见, 我们直接下载已经编译好的, 只用用于生产环境的Bootsrap

[下载地址参考](http://v3.bootcss.com/getting-started/#download)


![](http://o7cqr8cfk.bkt.clouddn.com/17-10-19/2353136.jpg)

## CDN加速服务器

Bootstrap 中文网 联合 又拍云 共同为 Bootstrap 专门构建了免费的 CDN 加速服务，访问速度更快、加速效果更明显、没有速度和带宽限制、永久免费。

```html
<!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

<!-- 可选的 Bootstrap 主题文件（一般不用引入） -->
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">

<!-- 最新的 Bootstrap 核心 JavaScript 文件 -->
<script src="https://cdn.bootcss.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
```

# 预编译版本包含的内容

下载压缩包之后，将其解压缩到任意目录即可看到以下（压缩版的）目录结构：

```
bootstrap/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   ├── bootstrap.min.css.map
│   ├── bootstrap-theme.css
│   ├── bootstrap-theme.css.map
│   ├── bootstrap-theme.min.css
│   └── bootstrap-theme.min.css.map
├── js/
│   ├── bootstrap.js
│   └── bootstrap.min.js
└── fonts/
    ├── glyphicons-halflings-regular.eot
    ├── glyphicons-halflings-regular.svg
    ├── glyphicons-halflings-regular.ttf
    ├── glyphicons-halflings-regular.woff
    └── glyphicons-halflings-regular.woff2
```

上面展示的就是 Bootstrap 的基本文件结构：

预编译文件可以直接使用到任何 web 项目中。我们提供了编译好的 CSS 和 JS (bootstrap.*) 文件，还有经过压缩的 CSS 和 JS (bootstrap.min.*) 文件。

同时还提供了 CSS 源码映射表 (bootstrap.*.map) ，可以在某些浏览器的开发工具中使用。

同时还包含了来自 Glyphicons 的图标字体，在附带的 Bootstrap 主题中使用到了这些图标。

# 基本模板

拷贝并粘贴下面给出的 HTML 代码，这就是一个最简单的 Bootstrap 页面了。

**要重复了解模板中的每一行代码!**

```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://cdn.bootcss.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <h1>你好，世界！</h1>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>

```










