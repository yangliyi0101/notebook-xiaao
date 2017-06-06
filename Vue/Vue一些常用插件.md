## Vue中常用的插件及其用法

[better-scroll滚动](#1)


<h3 id='1'>better-scroll滚动插件</h3>

[better-scroll Github地址](https://github.com/ustbhuangyi/better-scroll)

####使用方法



```js
<script type="text/ecmascript-6">
  import BScroll from 'better-scroll';
  
  let show = !this.fold;
  if (show) {
          this.$nextTick(() => {
            if (!this.scroll) {
              this.scroll = new BScroll(this.$refs.listContent, {
                click: true
              });
            } else {
              this.scroll.refresh();
            }
          });
        }
</script> 
```

