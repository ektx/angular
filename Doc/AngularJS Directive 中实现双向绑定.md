在使用 Directive 开发，我们通常都需要把我们组件内处理过的内容，最终返回给父级可以使用，而我们使用 `ng-model` 或是 `ng-value` 开发时，都不能自然的返回内容。

因此，我们需要进行以下的设置：

假定你有一个 directive 如下:

```js
function MyDirective () {
    return {
        restrict: 'E',
        scope: {
            value: '=ngValue'
        },
        templateUrl: '.../index.html',
        link: function(scope, ele, attrs) {
            //...
        }
    }
}
```

此时，我们的 directive 可以从父级接受到一个 `ng-value`, 我们在组件内部通过，`scope.value`可以访问到此值，父级中如下：

```html
<html ng-app="app">
<body ng-controller="my-cont">
    <my-directive nh-value="value"></my-directive>
</body>
<script>
angular.module('app', [])
.directive('myDirective', MyDirective)
.controller('myCont', function ($scope) {
    $scope.value = 123
})
</script>
</html>
```

此时，我们需要在我们的组件中添加如下方法，以实现双向的绑定功能
```js
link: function (scope, ele, attrs) {
    if (scope.value) scope.value = 234
}
```
