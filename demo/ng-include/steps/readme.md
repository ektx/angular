# ASteps

用于 AngularJs 1.x 中的流程导航功能。

## 使用

1. 引用样式表

   ```html
   <link rel="stylesheet" href="layout.css">
   ```

2. 添加 Directive

   ```javascript
   angular.directive(''asteps', function () {
       return {
           restrict: 'E',
           scope: {
               ngStepsData: '='
           },
           // 注意这里的路径，你可以使用你自己的路径来修改它
           template: '<div ng-include="\'steps.html\'"></div>'
       }
   })
   ```

3. 页面使用

   ```html
   <asteps ng-steps-data="root"></asteps>

   <script>
   angular.controller('myController', function($scope) {
       // ngStepsData Demo Data
       $scope.root = [
           {
               "title": "角实步你",
               "subTitle": "2018-03-23 09:04:35",
               "preview": "她矿较传已识采正打间决花交总此好活",
               "status": 1,
               "children": [
                   {
                       "title": "三统农",
                       "subTitle": "2018-03-23 09:04:35",
                       "preview": "观两用技难问就名调查",
                       "status": 1
                   },
                   {
                       "title": "并什较革科",
                       "subTitle": "2018-03-23 09:04:35",
                       "preview": "听近百由工县片张感究能住",
                       "status": 1
                   }
               ]
           },
           {
               "title": "变养",
               "subTitle": "2018-03-23 09:04:35",
               "preview": "及引点按车金收经半类示战林众民代",
               "status": 2,
               "children": [
                   {
                       "title": "求动周",
                       "subTitle": "2018-03-23 09:04:35",
                       "preview": "第接听代江好并际决按真位原口示",
                       "status": 1
                   },
                   {
                       "title": "十其不",
                       "subTitle": "2018-03-23 09:04:35",
                       "preview": "领深力什保加研象万向王细她产元你器却例",
                       "status": 3
                   },
                   {
                       "title": "活米写放",
                       "subTitle": "2018-03-23 09:04:35",
                       "preview": "选深候己研社造名打据复交研小受",
                       "status": 0
                   }
               ]
           },
           {
               "title": "保经",
               "subTitle": "2018-03-23 09:04:35",
               "preview": "日候铁二式些图格去火收及",
               "status": 0,
               "children": [
                   {
                       "title": "走计也次",
                       "subTitle": "2018-03-23 09:04:35",
                       "preview": "在决量党会快值支越些及毛派发立次也只",
                       "status": 0
                   }
               ]
           }
       ]
   })
   </script>
   ```

   ngStepsData 接受一个数组内容。



## ngStepsData 说明

| 参数     | 类型                             | 说明     |
| -------- | -------------------------------- | -------- |
| title    | String                           | 标题     |
| subTitle | String                           | 二级标题 |
| preview  | String                           | 预览     |
| status   | [1 完成，2 当然，3 失败，0 等待] | 状态     |
| children | Array                            | 子级内容 |

> children 的嵌套目前只支持2级，多级效果不佳

