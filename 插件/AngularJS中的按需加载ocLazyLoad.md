### AngularJS中的按需加载ocLazyLoad
    
    
    
参考来源:http://www.cnblogs.com/BestMePeng/p/AngularJS_ocLazyLoad.html
        https://segmentfault.com/a/1190000009650471
        
angularJsshiyong ocLazyLoad懒加载有四种加载方式
1、路由加载文件（比较常用，接下里主要讲这种）


```js
resolve:{
    deps:["$ocLazyLoad",function($ocLazyLoad){
         return $ocLazyLoad.load([所需加载的文件]);//路径一定要正确
    }]
}
```


2、控制器加载

3、依赖加载

4、模板template加载