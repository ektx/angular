[toc]

# Angular directive 定义
```js
app.directive('directiveName', function () {
    return {
        // config
    }
})
```

# Config 设置

## restrict
用于设置定义指令的展现形式

```html
<!-- E (element) -->
<directiveName></directiveName>

<!-- A (attribute) -->
<div directiveName></div>

<!-- C (class) -->
<div class="directiveName"></div>

<!-- M (comment) -->
<!--directive:directiveName expression-->
```

默认值为：`restrict:'EA'`, 表示可以在DOM里面使用元素形式或属性形式声明。一般来说，如果你想创建一个自己的模块的组件时，则使用元素形式，但是仅仅是为已有元素添加功能的话，就使用属性名。

> 如果想要支持IE8，则最好使用属性和类形式来定义，另外从angular 1.3.X开始，已经放弃支持IE8了。

## 参考

[Angular directive 实例详解](https://segmentfault.com/a/1190000005851663)