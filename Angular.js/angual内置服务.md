### angular内置服务

### 总表

| 名字 | 说明 |
| :---: | :--- |
| $anchorScroll | 滚动浏览器至指定的锚点 |
|  |  |
|  |  |
| $compile | 将HTML字符串或DOM编译为模板并生成模板函数 |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |

#### 1、$anchorScroll

滚动浏览器窗口至指定的锚点

具体参考：[API ](http://docs.ngnice.com/api/ng/service/$anchorScroll)  [Angular API 中文](http://www.jianshu.com/p/9cd7c2d2710f)

```js
$scope.gotoBottom = function() {

        // 将location.hash的值设置为
        // 你想要滚动到的元素的id
        $location.hash('bottom');

        // 调用 $anchorScroll()
        $anchorScroll();

    };
```

4、$compile

将HTML字符串或DOM编译为模板并生成模板函数，然后可以通过scope和模板链接在一起。

```js
let parkingAPP = require('../../../script/main.js');

parkingAPP.controller('day11Ctrl', function ($rootScope, $scope, $state, $log, $timeout, $compile) {

    let html = `<a href='www.github.com'>点击</a>`;
    let link = $compile(html);
    var node = link($scope);
    $('#html1').append(node);

});
```

$scopile 还允许接收其他参数

```js
function compile(tElement, tAttrs, transclude) { ... }
```

具体 使用方法参考： [API](http://docs.ngnice.com/api/ng/service/$compile)   以及    [邹业盛原创Compile的细节](https://checkcheckzz.gitbooks.io/angularjs-learning-notes/content/chapter18/18-5.html)

