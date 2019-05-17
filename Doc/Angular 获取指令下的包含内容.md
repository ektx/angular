当我们创建一个指令时,同时给了指令具有包含内部元素的能力,我们要如何得知内容呢?

```html
<div editable>
    <h1>Lorem Ipsem</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
    <clock>A custom directive</clock>
</div>
```

其实,在指令的 link 方法中,第5个参数就是包含内容,以下就是具体的代码:

```js
.directive('editable', function() {
    return {
       transclude: true,
       link: function(scope, element, attrs, ctrl, transclude) {
           transclude(scope, function(clone) {
               // clone is your transluded content
               // clone 就是你包含的内容
           });
       }
    };
});
```