## flex
```html
<div class="box">
    <div class="header">header</div>
    <div class="container">
		<div class="left column" >left</div>
		<div class="center column" >center</div>
		<!-- center居中 -->
        <div class="right column" >right</div>
     </div>
    <div class="footer">footer</div>
</div>

<style>
*{margin:0;padding:0;}
html,body{h100%;w100%}
.header{//大小,bgco}
.container{
	//大小,bgco
	display:flex;flex-direction:row;
}
.left{//大小,bgco}
.center{//大小,bgco}
.right{//大小,bgco}
.footer{//大小,bgco}
</style>
```

### [lab](../../../../../lab/圣杯-双飞翼/圣杯-flex.html)

---

## 定位+浮动
```html
<style>	
	body{width: 900px} 
	.header,.footer{height:30px;width:100%;background-color:red;}
	.center,.left,.right{height:300px;width:300px}
	.center{
        background-color:green;
		float:left
	}
	/* 通过margin+相对定位设置位置 */
	.left{
        background-color:yellow;
		float:left;
		margin-left:-100%;//左大小
		position:relative;
		left:-300px  //左大小
	}
	.right{
        background-color:blue;
		float:left;
		margin-left:-100%;/右大小
		position:relative;
		left:300px ;//中大小
	}
	/* 两边留白 */
	.container{
		padding-left:300px; //左大小
		padding-right:300px;//右大小
	}
	.container::after{
		content:"";
		display:block;
		clear:both;
	}
</style>
<div class="header">header</div>
    <div class="container">
        <div class="center">center</div>
        <div class="left" >left</div>
        <div class="right" >right</div>
    </div>
<div class="footer">footer</div>

```

### [lab](../../../../../lab/圣杯-双飞翼/圣杯.html)
