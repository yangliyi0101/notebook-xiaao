ng-directive指令

ng的指令非常的多，具体的可以去看API，中文的也可以，这边就列出个人觉得没用过的，经常出错的，需要注意的一些指令。

# `ngBindhtml`

通一个安全的方式将内容绑定到 HTML 元素上，直接使用的话会报一个Attempting to use an unsafe value in a safe context的安全错误，使用的时候用$sce.trustAsHtml\(\) 将html内容放进去。

# `ngBindtemplate`

用于告诉 AngularJS 将给定表达式的值替换 HTML 元素的内容，当你想在 HTML 元素上绑定多个表达式时可以使用`ng-bind-template`指令

