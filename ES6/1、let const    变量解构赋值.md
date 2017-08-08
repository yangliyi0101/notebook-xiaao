
## let const 新特点
###[参考阮一峰](http://es6.ruanyifeng.com/#docs/let#基本用法)
###暂时性死区
只要块级作用域内存在let命令，它所声明的变量就“绑定”（binding）这个区域，不再受外部的影响。

```js
var tmp = 123;

if (true) {
  tmp = 'abc'; // ReferenceError
  let tmp;
}
```

上面代码中，存在全局变量`tmp`，但是块级作用域内`let`又声明了一个局部变量tmp，导致后者绑定这个块级作用域，所以在let声明变量前，对tmp赋值会报错.

ES6明确规定，如果区块中存在let和const命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。


```js
if (true) {
  // TDZ开始
  tmp = 'abc'; // ReferenceError
  console.log(tmp); // ReferenceError

  let tmp; // TDZ结束
  console.log(tmp); // undefined

  tmp = 123;
  console.log(tmp); // 123
}
```

“暂时性死区”也意味着`typeof`不再是一个百分之百安全的操作。


```js
typeof x; // ReferenceError
let x;
```

`let`不允许在相同作用域内，重复声明同一个变量。


##变量的解构赋值

###对象的解构赋值


```js
var { foo: baz } = { foo: 'aaa', bar: 'bbb' };
baz // "aaa"

let obj = { first: 'hello', last: 'world' };
let { first: f, last: l } = obj;
f // 'hello'
l // 'world'
```
这实际上说明，对象的解构赋值是下面形式的简写（参见《对象的扩展》一章）


```js
let { foo: foo, bar: bar } = { foo: "aaa", bar: "bbb" };
```
也就是说，对象的解构赋值的内部机制，是先找到同名属性，然后再赋给对应的变量。真正被赋值的是后者，而不是前者。


```js
let { foo: baz } = { foo: "aaa", bar: "bbb" };
baz // "aaa"
foo // error: foo is not defined
```
上面代码中，foo是匹配的模式，baz才是变量。真正被赋值的是变量baz，而不是模式foo。

####对象的解构赋值的嵌套

数组一样，解构也可以用于嵌套结构的对象


```js
var node = {
  loc: {
    start: {
      line: 1,
      column: 5
    }
  }
};

var { loc, loc: { start }, loc: { start: { line }} } = node;
line // 1
loc  // Object {start: Object}
start // Object {line: 1, column: 5}
```
上面代码有三次解构赋值，分别是对loc、start、line三个属性的解构赋值。注意，最后一次对line属性的解构赋值之中，只有line是变量，loc和start都是模式，不是变量。

如果解构模式是嵌套的对象，而且子对象所在的父属性不存在，那么将会报错。



```js
// 错误的写法
let x;
{x} = {x: 1};
// SyntaxError: syntax error
```
上面代码的写法会报错，因为 JavaScript 引擎会将{x}理解成一个代码块，从而发生语法错误。只有不将大括号写在行首，避免 JavaScript 将其解释为代码块，才能解决这个问题。


```js
// 正确的写法
let x;
({x} = {x: 1});
```

####4 数值和布尔值的解构赋值

数值和布尔值的包装对象都有toString属性,解构赋值时，如果等号右边是数值和布尔值，则会先转为对象。
####5.函数参数的解构赋值
函数的参数也可以使用解构赋值,参数会被解析为变量
####6.圆括号的问题
尽量不使用圆括号。

