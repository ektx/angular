# $destroy

## 在指令中使用
通常我们在开发指令时，都会添加众多的事件与方法，有可能还需要添加到对 `document` 的事件监听，而当我们离开或注销组件时，事件却没有消失，他们还在页面中，久而久之，就会导致页面的事件越来越多，最终拖慢系统导致浏览器崩溃。

方法一：
```js
// 我们在 directive 中添加了全局的点击事件，用于帮助我们在点击非组件时
// 移除显示内容
var fun = function () {
    console.log(1)
    scope.$apply(function () {
        scope.show = false
    })
}

document.addEventListener('click', fun, false)

// 我们监听，在组件注销时，我们对此组件的作用域清空
element.on('$destroy', function () {
    scope.$destroy()
    document.removeEventListener('click', fun, false)
})
```