## 前端JS实现excel表格导入处理成json数组

Github：\[[SheetJS](https://github.com/SheetJS)/[**js-xlsx**](https://github.com/SheetJS/js-xlsx)\]

参考：[纯前端利用 js-xlsx 实现 Excel 文件导入导出功能示例](http://www.jianshu.com/p/74d405940305)

#### 1、安装/引用

下载`xlsx.full.min.js`到本地引用，或者 `npm install` 安装，采用哪一种方法都可以，这里不再叙述，不懂的可以自行百度

#### 2、上手

个人是在angularJS框架的控制器中使用的的，文件上传采用了已有的 `ng-file-upload` 插件上传，代码在在angular环境下的，其他环境的可以参考[纯前端利用 js-xlsx 实现 Excel 文件导入导出功能示例](http://www.jianshu.com/p/74d405940305),里面有详细的基于源生代码。

###### html中引入`angular`、`ng-file-upload`、`js-xlsx`

```html
<script src="vender/angular-1.5.6/angular.js" type="text/javascript"></script>
<script src="vender/ng-file-upload/ng-file-upload.js" type="text/javascript"></script>
<script src="vender/ng-file-upload/ng-file-upload-shim.js" type="text/javascript"></script>
<script src="vender/js-xlsx/xlsx.full.min.js" type="text/javascript"></script>
```

###### html

```js
<div class="buttonbox">
    <span class="fileNameDisplay btn" ng-if="excelNameDisplay">{{f.name}}</span>
    <button class="btn btn-sm btn-default" type="file" ngf-select="uploadFiles($file, $invalidFiles)"
            accept=".xls,.xlsx" ngf-max-size="5MB">
        <span class="glyphicon glyphicon-import font-blue-linewell"></span>导入
    </button>
    <a href="/views/gateway/excel/网关模板.xlsx">
        <button class="btn btn-sm btn-default">
                <span class="glyphicon glyphicon-export font-blue-linewell"></span>模板下载
            </button>
    </a>
</div>
```



