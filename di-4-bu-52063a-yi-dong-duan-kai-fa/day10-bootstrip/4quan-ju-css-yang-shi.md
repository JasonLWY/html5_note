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

# 布局容器

Bootstrap 需要为页面内容和栅格系统包裹一个 `.container` 容器。我们提供了两个作此用处的类。注意，由于 `padding` 等属性的原因，这两种 容器类不能互相嵌套。

.container 类用于固定宽度并支持响应式布局的容器。

```html
<div class="container">
  ...
</div>
```

.container-fluid 类用于 100% 宽度，占据全部视口（viewport）的容器。

```html
<div class="container-fluid">
  ...
</div>
```

# 栅格系统(`Grid system`)

Bootstrap 提供了一套响应式、移动设备优先的流式栅格系统，随着屏幕或视口（viewport）尺寸的增加，系统会自动分为最多12列。它包含了易于使用的预定义类，还有强大的mixin 用于生成更具语义的布局。
























