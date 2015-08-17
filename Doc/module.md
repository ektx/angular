## angular.module

应用开发模块  

angular.module(name, [requires], [configFn]);  

@name   模块名称  

@requires   需要包含使用的模块，譬如ngRoute路由模块,这里是一组数组列表,并且这些模块会在本模块加载之前由注入器进行预加载.  

@configFn   可以选择的功能模块，功能和module.config类似

#### controller

controller是angular.module()的方法

`angular.module(name, []).controller(name, constructor)`  

@name 是控制器名  

@constructor  处理函数  

示例：[demo](../demo/helloWorld2.html)  



#### $rootScope & $scope

`$rootScope`是AngularJs中最接近全局作用域的对象.

`$scope` 对象就是普通的Js对象,我们可以随意的修改或添加属性.在Ajs中,`$scope`充当数据模型,不同的是`$scope` 并不操作与处理数据,它只是`视图`和`控制器`之间的桥梁.

