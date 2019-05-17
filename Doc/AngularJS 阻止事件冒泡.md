```html
<table>
  <tr ng-repeat="user in users" ng-click="showUser(user)">
    <td>{{user.firstname}}</td>
    <td>{{user.lastname}}</td>
    <td>
      <button class="btn" ng-click="deleteUser(user.id, $index); $event.stopPropagation();">
        Delete
      </button>
    </td>              
  </tr>
</table>
```

[AngularJS ng-click stopPropagation](https://stackoverflow.com/questions/20300866/angularjs-ng-click-stoppropagation)