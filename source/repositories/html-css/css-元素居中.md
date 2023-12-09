## 父弹性 子margin:auto
```css
.outer{display:flex}
.inner{margin:auto}
```

## 定位
父级相对定位，子级绝对定位
```css
.outer{position: relative;}
.inner{
	position:absolute;
	left:0;rigth:0;top:0;bottom:0;
	margin:auto
}
```

## 定位+transform
```css
.outer{position: relative;}
.inner{
	position:absolute;
	left: 50%;top: 50%;
	transform: translate(-50%,-50%);
}
```

## 弹性盒
```css
.outer{
	display: flex;
	justify-content: center;
	align-items: center;
}
.inner{}
```

## 网格布局
[CSS 网格布局](https://www.runoob.com/css3/css-grid.html)
```css
.outer{
	display: grid;
	justify-content: center;
    align-items: center;
}
```