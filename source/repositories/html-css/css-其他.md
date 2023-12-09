## 可继承
* 文本(行高，字重，颜色)
* 列表（表头点）
* 字体
* 可见性
* list-style
* cursor

## 清除浮动
```css
.clear::after{
	content:'';
	display:block;
	clear:both;
}
```

## 选择器
>同级选靠后（覆盖）
> !important  >  内联样式  >  \#id >  伪类 > 属性 = class > 元素

## a:link a:visited a:hover a:active 顺序
a:link：没点击过
>顺序：  L V H A

## 变量
```css
:root{//全局变量
	--my-var:value;
}
p{
	height:var(--my-var)
}
```

## 文档流
> 一个“默认”状态。文档流指的是元素排版布局过程中，元素会自动从左往右，从上往下的流式排列。  

- 脱离文档流:
- 浮动 绝对定位 固定定位