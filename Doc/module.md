### angular.module
应用开发模块  
angular.module(name, [requires], [configFn]);  
@name   模块名称  
@requires   需要包含使用的模块，譬如ngRoute路由模块  
@configFn   可以选择的功能模块，功能和module.config类似

#### controller  
controller是angular.module()的方法
`angular.module(name, []).controller(name, constructor)`  
@name 是控制器名  
@constructor  处理函数  

示例：[demo](../demo/helloWorld2.html)  

