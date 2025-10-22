# BFC

全称是 块级格式化上下文。是一个独立的渲染区域，决定了元素的布局样式

1. **创建BFC**
   - 由一些特定的 CSS 属性触发（满足一个就可以）
     - float 属性的元素
     - position: absolute/fixed
     - display: inline-block, flex/inline-flex 等
     - overflow 不是 visible
2. **特性**
   1. BFC 中的元素和外部元素相互隔离，即使外部元素发生布局变化
3. **作用**
   1. 防止margin塌陷/重叠
   2. 自适应布局
   3. 避免外部浮动的影响