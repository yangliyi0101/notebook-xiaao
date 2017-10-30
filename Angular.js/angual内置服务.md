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



