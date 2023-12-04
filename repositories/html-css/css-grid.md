## [CSS Grid网格布局全攻略](https://juejin.cn/post/6844903891079790600)

## [布局速查](https://css-tricks.com/wp-content/uploads/2022/02/css-grid-poster.png)

```css
.parent { 
	display: grid;
	grid-template: 100px 100px 100px / 100px 100px 100px; //块长宽
	grid-gap: 10px 10px; //间隔
	justify-items: center; align-items:center;//居中
	grid-template-areas: "a b c" "d e f" "g h i";//区域名
}
```

```css
/* 指定起始行，结束行，起始列，结束列 */
.child:first-child {
	grid-row-start: 1; 
	grid-row-end: 2; 
	grid-column-start: 1; 
	grid-column-end: 3; 
} 
/* 使用缩写形式 */ 
.child:nth-child(2) { 
	grid-row: 2/3; 
	grid-column: 2/4;
} 
/* 直接指定区域名 */ 
.child:nth-child(3) { 
	grid-area: i; 
}
```

```css
/* 列对齐 */ 
.child:nth-child(1) { align-self: end; } 
/* 行对齐 */ 
.child:nth-child(2) { justify-self: end; } 
/* 采用缩写形式 */ 
.child:nth-child(3) { place-self: center center; }

```

## align-self justify-self:覆盖align-items justify-item