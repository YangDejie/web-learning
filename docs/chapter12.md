<h1>第**12**章   层叠式样式表**CSS**</h1>

- CSS是Cascading Style Sheets（层叠样式表单）
- 表现与内容分离


- - HTML的Tag主要是定义网页的内容(Content)，而CSS决定这些网页内容如何显示(Layout)。


- 创建层叠样式表的四种方法，优先级
#15.1样式表


- 是放置在网页HEAD部分的格式指令的集合

- - <style type="text/css">和</style>分别被浏览器识别为CSS的开始和结束，

  - 通过改变样式表可以改变网站的外观

  - - 使用样式可以做出影响HTML多个元素的改变，
    - 或者对整个文档进行样式的改变，
    - 也可以周期性地改变样式。

- ```
  <html>
  <head>
  <style type="text/css">
  <!--
    a {text-decoration:none; /* 下划线：underline; none */
         background:green;    /* 背景色*/
  	   color:blue;        /* 前景色*/
         corsur:hand;
         font-size:20pt}          /* 字体大小*/
  body {text-decoration:underline;background-color:#ddccff ;
  color:blue;font-weight:bold}
  -->
  </style>
  </head>
  <body>
  使用CSS的一个简单实例。<br>
  </body>
  </html>
  ```


# 15.2 层叠样式表 ★

- CSS层叠样式表（Cascading Stylesheet）指的是在一个单一的文件中使用多个样式定义。
- 一个样式表文件可以链接到网站的每一个文档，因此可以控制整个网站的外观。
- 术语Cascading（层叠）指的是继承或者在链接的、导入的、内嵌的以及内联样式之间的等级关系。
- 优先级


- - 在任何一个链接的文档中的样式定义会覆盖链接的样式表。

# 12.3 CSS基本语法 ★

- CSS的描述部分是由三部分组成的，分别是选择器、属性和属性值：


- - 选择器(selector) { 属性(Property): 属性值(Value); }
  - ![](https://ww4.sinaimg.cn/large/006y8lVajw1fbg6p3z1pjj30dj03nmxd.jpg)



# 12.4 CSS定义和使用方式 ★★

定义和使用样式 的4种方法：

- 外部样式表


- - 文件链接
  - 导入样式信息


- 内部样式表
- 内嵌样式

```
<html>
<head>
<style type="text/css">
<!--
  a {text-decoration:none; /* 下划线：underline; none */
       background:green;    /* 背景色*/
	   color:blue;        /* 前景色*/
       corsur:hand;
       font-size:20pt}          /* 字体大小*/
body {text-decoration:underline;background-color:#ddccff ;
color:blue;font-weight:bold}
-->
</style>
</head>
<body>
使用CSS的一个简单实例。<br>
</body>
</html>
```

- 内部样式表是写在HTML的`<head></head>`里面的，只对所在的网页有效。
- 使用内部样式表可能是使用样式最简单的方法。
- 使用`<STYLE>`标记符在HTML文档的head部分放置信息。
- 样式信息包含在注释标记符“`<!--    -->`”中
- 内嵌样式是混合在HTML标记里使用的，
- 用这种方法，可以很简单的对某个元素单独定义样式，只对所在的Tag有效。
- 内嵌样式的使用是直接在HTML标记里加入style参数，而style参数的内容就是CSS的属性和值
- 只适合用于偶然的样式改变。
- 最优先

```
<html>
<head>
<title>CSS的一个简单实例</title>
<style type="text/css">
<!--
body {text-decoration:underline;background-color:#ddccff ;
color:blue;font-weight:bold}
-->
</style>
</head>
<body>
使用CSS的一个简单实例。<br>
<span style="background-color:#ff0000;color:yellow;font-size:30pt">这是一个使用CSS修饰文字的简单实例</span>
</body>
</html>
```

- 在style参数后面的引号里的内容相当于在样式表大括号里的内容。
- 注意：style参数可以应用于任意BODY内的元素（包括BODY本身）。
- 使用内嵌样式的好处是可以在一个单一标记符中指定一个属性集合，但只适合用于偶然的样式改变。



- 外部文件  *.css


- - 链入
  - 导入

```
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>CSS的一个简单实例</title>
<link rel=stylesheet type="text/css" href="sample-1505.css">
</head>
<body>
<a href="http://www.cs.sdu.edu.cn">计算机科学与技术学院</a><br>
<span style="background-color:#ff0000;color:yellow;font-size:30pt">这是一个使用CSS修饰文字的简单实例</span>
</body>
</html>
```

css:

```
<style type="text/css">
<!--
  a {text-decoration:none; /* 下划线：underline; none */
       background:green;    /* 背景色*/
	   color:blue;                  /* 前景色*/
       corsur:hand;
       font-family:隶书;
       font-size:20pt}          /* 字体大小*/
  body {text-decoration:underline;background-color:#ddccff ;
          color:blue;font-weight:bold}
-->
</style>
```

## **class**和**id**用法 ★

- 如果不希望标记的所有样式都被修改
- 需要用到两个标记属性：class和id。
- id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。
- 指定


- - h1.title{font-weight: bolder; text-align: center;}
  - h1#navigator {font-size: 14px; text-align: left;}



```
<head>
	<title>演示CSS</title>  
	<style type="text/css">
		<!--   
        	h1.title {font-weight: bolder; text-align: center;} 
			h1#navi {font-size: 12px; font-weight: bolder; text-align: left;} 
			h1.news {font-size: 16px; font-weight:bold; text-align: center; color:green;}
		-->
	</style>
</head>
<body>
	<h1 class="title">这是页面最上端的标题</h1> 
	<h1 id="navi">这是页面左侧标题，用来导航</h1>   
	<h1 class="news">这是页面新闻的标题</h1>  
</body>  
```

- 层叠性就是继承性，


- - 样式表的继承规则是外部的元素样式会保留下来继承给这个元素所包含的其他元素


- 当样式表继承遇到冲突时，总是以最后定义的样式为准。
- 样式(Styles)的优先级依次是内嵌样式、内部样式、外部样式、浏览器缺省。



# 12．5  CSS样式 ★

- CSS 用于控制网页的样式和布局。
- CSS3 是最新的 CSS 标准。
- CSS常用样式


- - 背景
  - 文本属性，字体属性


- CSS框模型
- CSS定位

## 一、**CSS**常用样式**-**（**1**）**CSS**背景

- ![](https://ww3.sinaimg.cn/large/006y8lVajw1fbg6vzncgsj30gw0ag75q.jpg)

```
<head>
<style type="text/css">
body {background-color: yellow}
h1 {background-color: #00ff00}
h2 {background-color: transparent}
p {background-color: rgb(250,0,255)}
p.no2 {background-color: gray; padding: 100px;}
</style>
</head>
<body>
<h1>这是标题 1</h1>
<h2>这是标题 2</h2>
<p>这是段落</p>
<p class="no2">这个段落设置了内边距</p>
</body>
</html>
```

## 一、**CSS**常用样式**--** （**2**）**CSS**文本属性

![](https://ww4.sinaimg.cn/large/006y8lVajw1fbg6y6hyxgj30ip05owf9.jpg)

![](https://ww4.sinaimg.cn/large/006y8lVajw1fbg6xutcd6j30k204tgmb.jpg)



## 一、**CSS**常用样式**--** （**3**）**CSS**字体属性

![](https://ww4.sinaimg.cn/large/006y8lVajw1fbg6yl8cf2j30i00760tr.jpg)

```
<html>
<head>
<style>
h1
{
text-shadow: 5px 5px 5px #FF0000;
}
</style>
</head>
<body>
	<h1>文本阴影效果！</h1>
</body>
</html>
http://www.w3school.com.cn/tiy/t.asp?f=css3_text-shadow
```

## 二、CSS框模型 (Box Model)

- 文档树中的元素都产生矩形的框（Box），这些框影响了元素内容之间的距离、元素内容的位置、背景图片的位置等等。
- 而浏览器将这些框布局成访问者看到的样子。
- 确定了元素框处理元素内容、内边距、边框和外边距的方式。

```
<body>
<style type="text/css">  
.test_demo {overflow: scroll; height: 120px; width: 120px; background:#CCCCCC;}</style>
<div class="test_demo">  dfdfdfsfsdfsdfsdffghfg<br>hfghfghfghfghfghfghfghfghfgh</div>
</body>
```

![](https://ww3.sinaimg.cn/large/006tKfTcjw1fbg6zx25usj30id089ac5.jpg)





## 三、**CSS**定位

- CSS 为定位和浮动提供了一些属性，
- 利用这些属性，可以建立列式布局，将布局的一部分与另一部分重叠，
- 还可以完成多年来通常需要使用多个表格才能完成的任务。
- 定位的基本思想很简单，它允许你定义元素框相对于其正常位置应该出现的位置，或者相对于父元素、另一个元素甚至浏览器窗口本身的位置。



- CSS 有三种基本的定位机制


- - 普通流、浮动和绝对定位。
  - **position **属性


- 除非专门指定，所有框都在普通流中定位
- 块级框从上到下一个接一个地排列
- 一切皆为框


- - “块框” div、h1 或 p 元素
  - “行内框”span 元素. 它们的内容显示在行中，即。



普通流:

```
<body>
<h2 >这是带有绝对定位的标题</h2>
<p>通过绝对定位，元素可以放置到页面上的任何位置。下面的标题距离页面左侧 100px，距离页面顶部 150px。</p>
</body>
```

![](https://ww3.sinaimg.cn/large/006tKfTcjw1fbg79kzpflj30c605xq3b.jpg)

绝对定位:

```
<head>
<style type="text/css">
h2.pos_abs
{
position:absolute;
left:100px;
top:150px
}
</style>
</head>

<body>
<h2 class="pos_abs">这是带有绝对定位的标题</h2>
<p>通过绝对定位，元素可以放置到页面上的任何位置。下面的标题距离页面左侧 100px，距离页面顶部 150px。</p>
</body>
```

![](https://ww2.sinaimg.cn/large/006tKfTcjw1fbg7a4qebyj30ba05iq38.jpg)

浮动 float属性---调整屏幕大小

```
<head>
<style type="text/css">
h2.left
{float:left;}
h2.right
{float:right;}
</style>
</head>

<body>
<h2 class="left">标题1</h2>
<h2 class="right">标题2</h2>
<h2 >标题3</h2>
</body>
```

## 响应式布局RWD ★ 

- Responsive Web Design 
- RWD 能够以可变尺寸传递网页
- 平板和移动设备是必需的?
```html
<head>

 <style>

 .city { float: left; margin: 5px; padding: 15px; width: 300px; height: 300px; border: 1px solid black; } 

</style>

 </head> 

<body> 

<h1>W3School Demo</h1> 

<h2>Resize this responsive page!</h2> <br> 

<div class="city"> 

	<h2>London</h2> 

	<p>London is the capital city of England.</p> 

	<p>It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants.</p> 

</div>

 

<div class="city">

 <h2>Paris</h2> 

<p>Paris is the capital and most populous city of France.</p> 

</div> <div class="city"> <h2>Tokyo</h2> <p>Tokyo is the capital of Japan, the center of the Greater Tokyo Area, and the most populous metropolitan area in the world.</p> </div> </body> </html>
```
- Bootstrap 是一个用于快速开发 Web 应用程序和网站的前端框架。
- Bootstrap 是最流行的开发响应式 web 的 HTML, CSS, 和 JS 框架。
- 开源的
- http://www.runoob.com/bootstrap/bootstrap-intro.html

CSS3:

- [http://www.w3school.com.cn/tiy/t.asp?f=css3_transform_rotate](http://www.w3school.com.cn/tiy/t.asp?f=css3_transform_rotate)

```
<!DOCTYPE html>



<html>

<head>

<style> 

div

{

width:100px;

height:75px;

background-color:yellow;

border:1px solid black;

}

div#div2

{

transform:rotate(30deg);

-ms-transform:rotate(30deg); /* IE 9 */

-moz-transform:rotate(30deg); /* Firefox */

-webkit-transform:rotate(30deg); /* Safari and Chrome */

-o-transform:rotate(30deg); /* Opera */

}

</style>

</head>

<body>

<div>你好。这是一个 div 元素。</div>

<div id="div2">你好。这是一个 div 元素。</div>

</body>

</html>
```

- 动画是使元素从一种样式逐渐变化为另一种样式的效果。
- 请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%


- - 0% 是动画的开始
  - 100% 是动画的完成。


- http://www.w3school.com.cn/css3/css3_animation.asp
- http://www.w3school.com.cn/tiy/t.asp?f=css3_animation1