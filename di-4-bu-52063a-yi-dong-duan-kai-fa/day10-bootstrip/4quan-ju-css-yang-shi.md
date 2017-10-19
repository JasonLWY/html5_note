[参考页面](http://v3.bootcss.com/css/)

# 全部使用HTML5文档类型

```html
<!DOCTYPE html>
<html lang="zh-CN">
  ...
</html>
```

# 移动设备优先

Bootstrap 是移动设备优先的。

所以需要添加`viewport`数据标签

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

# 排版与链接

Bootstrap 排版、链接样式设置了基本的全局样式。分别是：

1. 为 `body` 元素设置 `background-color: #fff`;
2. 使用 `@font-family-base、@font-size-base 和 @line-height-base` 变量作为排版的基本参数
3. 为所有链接设置了基本颜色 `@link-color` ，并且当链接处于 `:hover` 状态时才添加下划线
这些样式都能在 `scaffolding.less` 文件中找到对应的源码。

# Normalize.css

为了增强跨浏览器表现的一致性，我们使用了 `Normalize.css`，这是由 Nicolas Gallagher 和 Jonathan Neal 维护的一个CSS 重置样式库。

