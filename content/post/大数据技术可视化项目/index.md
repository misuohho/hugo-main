+++
date = '2025-02-22T16:50:39+08:00'
draft = true
title = '大数据技术可视化项目'

+++

### flex使用

```javascript
 flex-direction: column; #从上到下对齐
 flex-direction: column-reverse; #从下到上对齐
 flex-direction: row; #从左到右对齐 （默认）
 flex-direction: row-reverse; #从右到左对齐
```



```javascript
.container{
    width: 100%;
    height:98%;
    display: flex;
    background-color: blueviolet;
}
.item{
    flex: 1;
    background-color: aqua;
    border: 1px solid white;
}
.item1{
    flex: 2;
    background-color: aqua;
    border: 1px solid white;
}
```

<img src="page/flex.png" style="zoom:80%;" />

```javascript
<template>
<div class="container">
    <div class="item" style="flex: 0 1 30%;">1</div> #可以在标签设置内百分比
    <div class="item" style="flex: 0 1 40%;">2</div>
    <div class="item" style="flex: 0 1 30%;">3</div>
</div>
</template>

<script setup>

</script>

<style scoped>
.container{
    width: 100%;
    height:98%;
    display: flex;
    background-color: blueviolet;
}
.item{
    flex: 1;
    background-color: aqua;
    border: 1px solid white;
}
</style>
```

<img src="page/flex2.png" style="zoom:80%;" />

#### .containter为父元素盒子——item为子元素盒子

#### flex定义父元素盒子为弹性盒子（flex为从横向排列，默认为上下排列）

```javascript
.container {
  display: flex;
  /* 其他样式，如方向、换行、对齐等 */
  flex-direction: row; /* 可以是 row 或 column */
  flex-wrap: wrap;     /* 可以是 nowrap, wrap, 或 wrap-reverse */
  justify-content: space-between; /* 子元素在主轴上的对齐方式 */
  align-items: center; /* 子元素在交叉轴上的对齐方式 */
}
```

#### flex在子元素盒子中控制子元素的布局

```javascript
.item {
  flex: 1; /* 等同于 flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
  /* 或者更具体的设置 */
  flex-grow: 2; /* 子元素可以增长的空间比例 */
  flex-shrink: 1; /* 子元素可以缩小的空间比例 */
  flex-basis: auto; /* 子元素的起始大小 */

  /* 其他样式 */
  margin: 10px;
  padding: 20px;
}
```

