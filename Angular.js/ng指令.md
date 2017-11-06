ng-directive指令

ng的指令非常的多，具体的可以去看API，中文的也可以，这边就列出个人觉得没用过的，经常出错的，需要注意的一些指令。

# `ngBindhtml`

通一个安全的方式将内容绑定到 HTML 元素上，直接使用的话会报一个Attempting to use an unsafe value in a safe context的安全错误，使用的时候用$sce.trustAsHtml\(\) 将html内容放进去。

# `ngBindtemplate`

用于告诉 AngularJS 将给定表达式的值替换 HTML 元素的内容，当你想在 **HTML 元素上绑定多个表达式**时可以使用`ng-bind-template`指令

# `ngBlur`

当输入框失去焦点\(onblur\)时执行表达式。

注意：**ng-blur**指令不会覆盖原生的 onblur 事件， 如果触发该事件，**ng-blur**表达式与原生的 onblur 事件都会执行。

# `ngChange`

**ng-change**指令需要搭配`ng-model`指令使用。

**ng-change**事件在值的每次改变时触发，它不需要等待一个完成的修改过程，或等待失去焦点的动作。

**ng-change**事件只针对输入框值的真实修改，而不是通过 JavaScript 来修改

# `ngChecked`

**ng-checked**指令用于设置复选框\(checkbox\)或单选按钮\(radio\)的 checked 属性

# `ngClass`

`ng-class`指令的值可以是字符串，对象，或一个数组。

如果是字符串，多个类名使用空格分隔。

如果是对象，需要使用** key-value **对，key 是一个布尔值，value 为你想要添加的类名。只有在 key 为 true 时类才会被添加。

如果是数组，可以由字符串或对象组合组成，数组的元素可以是字符串或对象。

# `ngClasseven`

**ng-class-even**指令用于为 HTML 元素动态的绑定一个或多个 CSS 类，但只作用于偶数行。

**ng-class-even**指令需要与**ng-repeat**指令搭配使用。

**ng-class-even**指令建议用在表格的样式渲染中，但是所有HTML元素都是支持的。

# `ngClassodd`

同理，只作用于奇数行

# `ngClick`

# `ngCloak`

AngularJS 应用在加载时，文档可能会由于AngularJS 代码未加载完而出现显示 AngularJS 代码，进而会有闪烁的效果，**ng-cloak**指令是为了防止该问题的发生，可能我的测试方法有问题，没太看出来效果



