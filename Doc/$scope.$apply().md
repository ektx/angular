[TOC]

# 实例
在项目开发过程中，你可能需要对列表或数据进行修改展示，如：

```html
<div ng:app ng-controller="Ctrl">{{mes}}</div>

<script>
functionCtrl ($scope) {
    $scope.mes = 'hello world!'
    
    setTimeout(function () {
        $scope.mes = 'hi, man!'
    })
}
</script>
```

当是你会发现，数据可能并没有发生你预想的变化，此时我们可以使用 `$scope.$apply()`

```diff
+ $scope.$apply(function () {
    $scope.mes = 'hi,'
+ })
```

我们把要更新的内容包含到 apply 中，就可以了。

# 参考
[angularJS之$apply()方法](https://www.cnblogs.com/penghongwei/p/3398361.html)