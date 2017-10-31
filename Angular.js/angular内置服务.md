### [缓存服务](http://www.cnblogs.com/ys-ys/p/4967404.html)[缓存服务](http://www.cnblogs.com/ys-ys/p/4967404.html)[缓存服务](http://www.cnblogs.com/ys-ys/p/4967404.html)[缓存服务](http://www.cnblogs.com/ys-ys/p/4967404.html)[缓存服务](http://www.cnblogs.com/ys-ys/p/4967404.html)[缓存服务](http://www.cnblogs.com/ys-ys/p/4967404.html)angular内置服务

### 总表

| 名字 | 说明 |
| :---: | :--- |
| $anchorScroll | 滚动浏览器至指定的锚点 |
| $animate | 基本的DOM操作功能 |
| $cacheFactory | 缓存服务 |
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

#### 2、$animate

$animate服务提供了基本的DOM操作功能如在DOM里插入、移除和移动元素，以及添加和删除类。这个服务是ngAnimate的核心服务，为CSS和Javascript提供了高档次的动画。

参考：[API ](http://docs.ngnice.com/api/ng/service/$animate) [API中文](http://www.cnblogs.com/ys-ys/p/4987022.html)

#### 3、$cacheFactory

用于生成一个用来存储缓存对象的服务，并且提供对对象的访问

参考：[中文API](http://www.cnblogs.com/ys-ys/p/4967404.html)

值的注意的是，这是应用程序的缓存服务，而不是浏览器本地的缓存。所以当你刷新浏览器，初始化整个应用程序的时候，之前的缓存数据都会丢失。那么问题就来了，怎么才能刷新/初始化应用程序而不丢失之前保存的数据呢，这个可以使用localStorage或者cookies.

#### 4、$compile

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

#### 5、$controller

负责实例化控制器

6、$document

等同于`window.document`

7、$exceptionHandler

处理程序中出现的异常，不常用

8、$filter

过滤器 [中文API](http://www.cnblogs.com/ys-ys/p/5006951.html)

也可见filter过滤器介绍

9、 $http

http请求

详见$http请求数据

10、$httpBackend

11、**$interpolate**

将一个字符串编译成一个插值函数。HTML编译服务使用这个服务完成数据绑定。可以从其他地方获取到内容，处理绑定到对应的html中

[中文API](https://segmentfault.com/a/1190000002753321)  里面有详细的例子，这个服务一般是特定场合才会使用，个人感觉使用场合不是很高



