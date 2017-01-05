<h1>第**13**章**JavaScript**基础</h1>

# 13.1 什么是JavaScript ★

JavaScript是一种基于对象和事件驱动并具有安全性能的脚本语言。

4个基本特征：

- JavaScript是一种脚本语言


- - 它采用小程序段的方式实现编程。
  - JavaScript是一种解释性语言
  - JavaScript被直接嵌入 HTML 页面，被设计用来向 HTML 页面添加交互行为


- JavaScript是基于对象但不是面向对象的一种语言


- - 它不允许对象继承，也没有子类，
  - 它在功能上依赖于内建对象的集合 
  - 使用JavaScript，你可以创建自己的对象


- JavaScript是一种事件驱动的语言

**javascript能做什么？**

- （1）JavaScript 为 HTML 设计师提供了一种编程工具。
- （2）JavaScript 可以将动态的文本放入 HTML 页面。


- - `document.write("<h1>" + name + "</h1>")`


- （3）JavaScript 可以对事件作出响应。
- （4）JavaScript 可以读取及改变 HTML 元素的内容。
- （5）JavaScript 可被用来验证数据。在数据被提交到服务器之前，JavaScript 可被用来验证这些数据。
- （6）JavaScript 可被用来检测访问者的浏览器。JavaScript 可被用来检测访问者的浏览器，并根据所检测到的浏览器，为这个浏览器载入相应的页面。
- （7）JavaScript 可被用来创建、操作cookies。



JavaScript和Java ★

![](https://ww4.sinaimg.cn/large/006tKfTcjw1fbg7gnqjkjj30i30bsdim.jpg)

- VBScript是Microsoft开发的脚本语言
- VBScript是Visual Basic的一个子集
- Netscape Navigator不支持VBScript
- JavaScript既支持IE又支持Navigator
- JScript是Microsoft的Netscape JavaScript
- JScript也支持IE又支持Navigator


- ECMA Script
- Netscape和Microsoft都向欧洲计算机制造商协会（European Computer Manufacturers Association（ECMA））的脚本语言ECMA脚本靠拢。
- ECMAScript，这是一种国际标准化的JavaScript版本。
- 现在的主流浏览器都支持这种版本 



javasript优势：

- ①简单性
- ②动态性


- - 事件驱动


- ③跨平台性


- - JavaScript是依赖于浏览器本身，与操作环境无关


- ④节省CGI的交互时间

## JS引擎 ★

不同浏览器有不同的**JS**引擎：

- **Chakra ---IE**浏览器
- **SpiderMonkey--- Firefox **
- **SquirrelFish ---WebKit , Safari**浏览器** **
- **V8**引擎**---blink**浏览器内核


- - JavaScript程序在V8引擎下的运行速度媲美二进制程序



# 13.2 JavaScript使用方法 ★

```
<SCRIPT  LANGUAGE = "JavaScript">
        <!--Hide the SCRIPT from other browsers
                 {JavaScript程序}
       // Stop hiding from other browsers -->
</SCRIPT>
```

```
<SCRIPT  LANGUAGE = "JavaScript"        
  SRC="http://www.cs.sdu.cn/javascript/javaScript.js">
</SCRIPT>	
```

```
<HTML>
      <HEAD>
             <TITLE>JavaScript简单实例</TITLE>
             <SCRIPT  LANGUAGE = "JavaScript">
		    <!--Hide the SCRIPT from other browsers
			{JavaScript程序}
			// Stop hiding from other browsers -->
		</SCRIPT>
	</HEAD>
	<BODY>
		页面内容
		<SCRIPT  LANGUAGE = "JavaScript">
			<!--Hide the SCRIPT from other browsers
				{JavaScript程序}
			// Stop hiding from other browsers -->
		</SCRIPT>
		页面内容
	</BODY>
</HTML>
```

- `<SCRIPT>`标记符中的语言属性告诉浏览器将要读出的脚本类型，


- - 如果不加语言属性，Microsoft Internet Explorer和Netsacpe Navigator默认的语言属性是JavaScript。
  - 为了保证浏览器解释的脚本是JavaScript，建议总是加上语言属性。
  - 该属性也支持语言的指派版本，


- - - LANGUAGE=”JavaScript1.1”
    - type="text/javascript"



```
<html>
    <body>
	<script type="text/javascript">
	    document.write("Hello World!");
	    document.write("<h1>header</h1>");
	</script>
    </body>
</html>
```

内建对象继承关系

![](https://ww3.sinaimg.cn/large/006tNc79jw1fbg7jrk3aij30fx0cemxt.jpg)

# 13.3 JavaScript语法

- **JavaScript**语句与注释


- - 分号是可选的
  - 代码块以左花括号开始，以右花括号结束
  - 单行的注释以 // 开始，多行注释以 /* 开头，以 */ 结尾


- **JavaScript**变量


- - 可以不声明
  - 区分大小写
  - 必须以字母或下划线开始


- 运算符
- 条件语句
- 循环语句
- ​
- 变量有效期
- ​
- 异常

# 13.4 JavaScript函数

```
自定义函数
Function 函数名 （参数,变元）
	{
		函数体;.
		Return 表达式;
	}
```

```
<head>
  <script language = "JavaScript">	
      function getSum(a,b) 
        {return(a+b);}
   </script>
</head>
<body>
<script type="text/JavaScript">	document.write(getSum(8,2))
</script>
</body>
```

```
<HEAD>
<TITLE>函数实例</TITLE>
<script language=“javascript”>
function testQuestion(question) 
{
	var answer = eval(question);
	var output = "What is " + question + "?";
	var correct = '<IMG SRC = "correct.gif">';
	var incorrect = '<IMG SRC = "incorrect.gif">';
	var response = prompt(output,"0");
	return(response= =answer) ? correct:incorrect;
}
</script>
</HEAD>
<BODY>
<script language=“javascript”>
Var result=testQuestion(“10+10”);
Document.write(result);
</script>
</BODY>

eval() 函数计算 JavaScript 字符串，并把它作为脚本代码来执行
```

# 13.5 JavaScript事件 ★

```
  <body>

	  <input type="button" 	onclick="show_confirm()" 

		value="Show a confirm box" />

   </body>

</html>

```



- 事件驱动
- 自定义函数

```
<html>
    <head>
        <script type="text/javascript">
            function show_confirm()
		     {
               var r=confirm("Press a button!");
               if (r==true)  
			 {  alert("You pressed OK!");  }
		       else  
			 {  alert("You pressed Cancel!");  }
		     }
	    </script>
    </head>
```

确认框  **window.** confirm()

- Window 可省略
- 确认框用于使用户可以验证或者接受某些信息。
- 当确认框出现后，用户需要点击确定或者取消按钮才能继续进行操作。
- 如果用户点击确认，那么返回值为 true。如果用户点击取消，那么返回值为 false。

## JavaScript消息框 ★  

- 警告框、确认框、提示框。
- 给用户一个消息：方法alert()
- alert()方法是一个允许你和用户通信的简单JavaScript方法。
- 它是Window对象的一个方法
- alert()方法的语法如下：


- - alert(〞message〞)。

```
<SCRIPT LANGUAGE = "JavaScript">
<!--Hide the SCRIPT from other browsers
alert("Welcome to JavaScript")
// Stop hiding from other browsers -->
</SCRIPT>
```

prompt()方法的使用

```
<SCRIPT LANGUAGE = "JavaScript">
<!--Hide the SCRIPT from other browsers
prompt("What's your name", "yourname")
// Stop hiding from other browsers -->
</SCRIPT>
```

```
<Script Language="JavaScript">
	name=prompt("请输入你的名字:");
	alert ("早上好,"+name);
</Script>

JavaScript 对大小写敏感
变量必须以字母或下划线开始
```

open()方法

```
控制打开哪些窗口以及其所包含的文档。
open(“(URL)”, “(窗口名)”, “特征列表”);
window.open("new.html", "newWindow", "toolbar=yes,location=1,directories=yes,  status=yes,menubar=1,scrollbars=yes, resizable=0, width=200, height=200");
```

```
<html>
   <head>
        <script type="text/javascript">
            function open_win() 
               {window.open("http://www.w3school.com.cn")}
        </script>
    </head>
    <body>
         <input type=button 
               value="Open Window“ 
		    onclick="open_win()" />
    </body>
</html>
```

- toolbar创建标准的工具条
- location创建位置输入域
- directiries创建标准的目标按钮
- status创建状态条
- menubar创建在窗口顶端的菜单
- scrollbars当文档超过当前窗口时，创建滚动条
- resizable允许用户重新调整窗口大小
- width指定窗口的宽度，像素为单位
- height指定窗口的高度，像素为单位
- top指定在Internet Explorer 4和Navigator 4中打开窗口的屏幕顶端坐标的y坐标
- left指定在Internet Explorer 4和Navigator 4中打开窗口的屏幕顶端坐标的x坐标

```
<HTML>
    	<HEAD>
    		<TITLE> New Window </TITLE>
    </HEAD>
    <BODY>
    		<FORM>
   			 <INPUT TYPE="button"  VALUE="打开搜索引擎窗口" 
			onClick="newWindow=open(‘http://www.google.com’,
			‘google’,‘toolbar=0,location=1,
			menubar=1,scrollbars=1,resizable=1’) ">
	    </FORM >
	</BODY>
  </HTML>
使用OnClick事件被触发来自内联脚本的Open()方法
```

```
<html>
	<head>
		<title>一个简单的不带参数的JavaScript函数及其调用的示例代码</title>
		<script language = "JavaScript">
			function clickme()
				{
				alert("你好！")
				}
		</script>
	</head>
	<body>
		<div onclick = "clickme()">点击我吧</div>
	</body>
</html>
```

# 13.7 JavaScript对象 ★★

![](https://ww3.sinaimg.cn/large/006tNc79jw1fbg7ofsdtij30hb04l74y.jpg)

```
<script type="text/javascript">　
var txt="Hello World!"　document.write(txt.length)　document.write(str.toUpperCase())
</script>
```

![](https://ww1.sinaimg.cn/large/006tNc79jw1fbg7oz7gssj30ca0cnt97.jpg)

## 一、Navigator对象

- Navigator对象允许访问针对浏览器的信息
- ![](https://ww1.sinaimg.cn/large/006tNc79jw1fbg7pag0m9j30e405ot9h.jpg)

```
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>浏览器信息搜集</title>
<script language="JavaScript">
<!--
function yourBrowser()
{
document.details.Name.value=navigator.appName;
document.details.Version.value=navigator.appVersion;
document.details.Code.value=navigator.appCodeName;
document.details.Agent.value=navigator.userAgent;
}
-->
</script>
</head>
<body bgcolor="#FFFFFF">
<DIV align="center">
<TABLE border="1">
<FORM name="details">
<TR>       <TD>浏览器名称</TD>
	  <TD><input type="text" name="Name" size="50"</TD>
</TR>
<TR>       <TD>浏览器版本</TD>
	  <TD><input type="text" name="Version" size="50"</TD>
</TR>
<TR>       <TD>浏览器代码名称</TD>
	  <TD><input type="text" name="Code" size="50"</TD>
</TR>
<TR>       <TD>代理商名称</TD>
	  <TD><input type="text" name="Agent" size="50"</TD>
</TR>
<TR>      <TD><input type="button" value="测试浏览器"  
                      onClick="yourBrowser()"></TD>
</TR></FORM></TABLE></DIV></body>
</html>
```

### Robots协议★

- robots.txt文件是一个[文本](http://baike.baidu.com/view/300107.htm)文件
- 当一个搜索蜘蛛访问一个[站点](http://baike.baidu.com/view/391109.htm)时，它会首先[检查](http://baike.baidu.com/view/386571.htm)该站点[根目录](http://baike.baidu.com/view/1061154.htm)下是否存在robots.txt
- 由于该网站的robots.txt文件存在限制指令，系统无法提供该页面的内容描述
- [淘宝网](http://baike.baidu.com/view/1590.htm)的 Robots.txt文件


- - User-agent: Baiduspider
  - Disallow: /

### Modernizr ★

- Modernizr是一个开源的JS库


- - https://modernizr.com/
  - 使用 JavaScript 检测浏览器所支持的功能。
  - 根据设备状态，将最新的 CSS3 或 HTML5 功能嵌入你的网站


- 检测当前浏览器是否支持CSS3的特性


- -  @font-face、border-radius、 border-image、box-shadow、rgba() 等


- 检测是否支持[HTML5](http://www.mhtml5.com/)的 特性


- - audio、video、本地储存、和新的 标签的类型和属性等。

## 二、 Window 对象

- Window 对象表示浏览器窗口。
- 每当` <body>` 或者 `<frameset>` 标记出现，Window 对象就会被自动创建。
- 所有 JavaScript 全局对象、函数以及变量均自动成为 window 对象的成员
- 对话框，open，close，浏览器窗口的高度和宽度……
- Document, history, location

## 三、location 对象

```
window.location 对象用于获得当前页面的地址 (URL)，并把浏览器重定向到新的页面
<script> 
document.write(location.href); 
</script> 
```

加载新文档：

```
<script>
function newDoc() 
{ 
window.location.assign("http://www.w3school.com.cn")
 }
</script>

<body>
<input type="button" value="加载新文档" onclick="newDoc()">
</body>
```

```
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>浏览器重定向实例</title>
<script language="JavaScript">
<!--
function checkBrowser()
{
    var name=navigator.appName;
    if (name.indexOf('Netscape') != -1)  {
	    document.location.href="sample-1602-netscape.htm";
	}  else  {
                               if (name.indexOf('Microsoft') != -1) {
	                    document.location.href="sample-1602-microsoft.htm";
	                 }	
	            }
}
-->
</script>
</head>
<body bgcolor="#FFFFFF">
<p>
点击测试浏览器的命令按钮，将提示你使用的是何种浏览器。
</p>
<FORM METHOD="post" action=" ">
    <DIV align="center">
        <INPUT type="button" name="Button" value="测试浏览器"   
                      onClick="checkBrowser()">
    </DIV>
</FORM>
</body>
</html>
```

## 四、history对象

- window.history.back()
- window.history.forward()
- ![](https://ww2.sinaimg.cn/large/006tNc79jw1fbg7u19e2qj30hy035gm9.jpg)

## 五、document对象

- window.document指示页面上有什么信息

- 在Document下是Image和Form

- ```
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=gb2312">
  <title>浏览器重定向实例</title>
  <script language="JavaScript">
  <!--
  if (document.images) {  
  	one=new Image;
  	one.src="sample-1603-1.jpg";
  	oneOver=new Image;
  	oneOver.src="sample-1603-1over.jpg";
  	}
  -->
  </script>
  </head>
  <body bgcolor="#FFFFFF">

  <a href="sample-1602-microsoft.htm" onMouseOver="document.cert.src=oneOver.src"    onMouseOut="document.cert.src=one.src">
  <img width=70% height=70% src="sample-1603-1.jpg" name="cert" border=0> 
  </a>
  	
  </body>
  </html>
  ```



# 13.8 javascript 应用 ★

## 一、HTML DOM （Document Object Model for HTML）

![](https://ww2.sinaimg.cn/large/006tNc79jw1fbg7vayjixj30h60953z5.jpg)

- getElementById() 
- getElementsByTagName() 方法
- 或者使用一个元素节点的 parentNode、firstChild 以及 lastChild 属性。

```
<html>
  <body>
   <h1 id="id1">
      My Heading 1
   </h1>
  <button type="button" onclick="document.getElementById('id1').style.color='red'">
         点击这里！
   </button>
 </body>
</html>
```



二、**HTML5 - **使用地理定位

```
<html>
    <body>
          <p id="demo">点击这个按钮，获得您的坐标：</p>
           <button onclick="getLocation()">试一下</button>
<script>
var x=document.getElementById("demo");
```

![](https://ww4.sinaimg.cn/large/006tNc79jw1fbg7w50q7xj30fl07xwfb.jpg)

三、**JS**库

- JavaScript 库常被称为 *JavaScript *框架


- - jQuery


- - - 目前最受欢迎的 JavaScript 框架。
    - 使用 CSS 选择器来访问和操作网页上的 HTML 元素（DOM 对象）。
    - 提供 companion UI（用户界面）和插件。


- - Prototype


- - - 供用于执行常见 web 任务的简单 API


- - MooTools


- - - 提供了可使常见的 JavaScript 编程更为简单的 API
    -  也含有一些轻量级的效果和动画函数


- Google 为一系列 JavaScript 库提供了免费的 CDN，包括


- - jQuery


- - - 引用 **jQuery**

```
	<head> 

	    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js"> 

	    </script>

	 </head>

```



- - Prototype
  - MooTools
  - Dojo
  - Yahoo! YUI、