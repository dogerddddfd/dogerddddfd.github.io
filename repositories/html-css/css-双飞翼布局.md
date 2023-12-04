## 圣杯：padding留白，移动左右

## 双飞翼：子div，margin将center内容移动出来
```html
<style>
	body{width: 900px} 
	.header,.footer{height:30px;width:100%;background-color:red;}
	.center,.left,.right{height:300px;width:300px}
	.center{
		float:left
	}
	.center_inside{
		height:100%;width:100%;
		background-color:yellow;
		margin:0 300px
	}
	/* 通过margin+相对定位设置位置 */
	.left{
		background-color:green;
		float:left;
		position:relative;
		left:-300px
	}
	.right{
		background-color:blue;
		float:left;
	}
	.container::after{
		content:"";
		display:block;
		clear:both;
	}

</style>
<div class="header">header</div>
<div class="container">
	<div class="center ">
		<div class="center_inside">center</div>
	</div>
	<div class="left " >left</div>
	<div class="right " >right</div>
</div>
<div class="footer">footer</div>
```