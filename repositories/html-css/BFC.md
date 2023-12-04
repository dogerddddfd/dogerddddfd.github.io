# Block formatting context，块级格式化上下文

## 规则
- 块级元素
- 隔离的独立容器
- BFC区域不会与浮动元素发生重叠
- 标签外边距会发生重叠相加（一般是外边距取大）
- 计算BFC的高度时，浮动元素也参与计算

## 产生BFC
- 根元素：body（自带bfc）
- 元素设置浮动：float 除 none 以外的值；
- 元素设置绝对定位：position (absolute、fixed)；
- display 值为：inline-block、table-cell、table-caption、flex、inline-flex等；
- overflow 值为：hidden、auto、scroll；

## 应用/问题
* 解决高度坍塌
* margin溢出：子元素margin顶开父元素；父元素overflow:hidden
* margin重叠：BFC内部相邻的元素的margin会叠加；将其中一个设置为BFC
