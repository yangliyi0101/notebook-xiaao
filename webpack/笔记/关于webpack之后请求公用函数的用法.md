## 关于webpack打包之后请求公共变量/函数的用法

公用函数或者变量的`common.js`文件,dingy

```js
/**
 * Created by XiaAo on 2017/5/9.
 */



var zz = {
    name: 10,           //定义变量
    aa: function () {   //定义function aa();
        alert('aaaa');
    },
    bb: function () {   //定义function bb();
        alert("bbb");
    }
}

alert('hkjhjkhh');  //不用调用，直接就会执行


module.exports = zz;    //将zz暴露出去,可以让其他文件请求到


```

