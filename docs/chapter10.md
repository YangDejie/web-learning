<h1>第**10**章 **HTML**基础</h1>

# 1 HTML简介 ★

1. HTML语言

- Hypertext Mrakup Language（超文本标记语言）
- 是为网页创建和其它可在网页浏览器中看到的信息而设计的一种标记语言。
- HTML已经成为描述和显示网页的国际标准，
- 由万维网联盟（W3C）维护。
- HTML的一个重要特点是超级链接hyperlink
- 一个HTML文件的后缀名是.html或者是.htm
- HTML是一个纯文本格式的ASCII文件


- HTML不是一种编程语言，而是一种描述性的标记语言，
- 用于描述超文本中内容的显示方式。


- - 这些内容的描述都是通过HTML标记来完成的


- 标记：被用来结构化信息——例如标题、段落和列表等等，也可用来在一定程度上描述文档的外观和语义，比如图片的显示尺寸，文字的大小、颜色、字体等。

# 2 HTML标准与发展历史

- 万维网联盟World Wide Web Consortium，W3C，[http://www.w3c.org](http://www.w3c.org/)


- - W3C 制定的 web 标准并非强制而只是推荐标准。


- HTML标准定义了构成HTML语言的每一个独立元素以及这些元素是指示如何在浏览器中显示HTML文档中的指令和标记符。
- 这一标准确保在不同的浏览器和计算机平台上超文本显示的一致性

html起源：

- SGML（standard generalized markup language，标准通用标记语言）语言，


- - 于1986年获得国际标准化组织的批准。这种语言是为了在各种网络环境之间、不同文件格式之间进行交流而使用的一种语言格式。它的文件格式标准化，并统一使用标记符号（tag）对文件的内容进行标记。


- HTML于1991年问世，它是SGML的一个子集。
- HTML是一种有前后关系格式化的语言，因此在HTML中除了包含文本内容，还包含通常是成对出现的标记。
- 标记是包括在尖括号中的文本，为HTML的解释器提供指令。

Html版本

- HTML于1991年问世，它是在SGML基础上开发成功的，可以说它是SGML的一个子集。 
- 第一版——1993年6月草案（并非标准）
- HTML2.0：1995年11月发布 
- HTML3.2：1996年1月14日，表格、框架 
- HTML4.0：1997年12月18日，CSS，开访问性
- HTML4.01：1999年12月24日，XHTML
- HTML 5.0最新草案——2008年1月22日发布，支持HTML和XHTML。
- HTML 5.0——2012年12月17日，W3C推荐标准。“HTML5是开放的Web网络平台的奠基石。”
- ** W3C**还计划到**2016**年底发布后续版本**HTML 5.1**。 



# 3 HTML标记与属性 ★



- 标记（Tag）

标记由封装在小于号（<）和大于号（>）构成的一对尖括号之中，标记一般分首标记和尾标记，它们成对出现。

 例如：<u>text with underline</u> 

- - 开始标记，开启标记
  - 结束标记 ，关闭标记


- HTML文件结构  例子1


- - `<HTML></HTML>`之间包含头部(head)与实体(body)两大部分



# 4 HTML标记语法 ★

- 标记


- - 单标记，例如：`<br>`, `<hr>`
  - 双标记,  例如：`<a>…</a>`
  - 注释标记：`<!--注释内容-->`或`<!-->注释内容</!-->`
  - 通过属性扩展HTML元素的描述能力


- 标记属性

<标记 属性1="属性值" 属性2="属性值" 属性3="属性值"…> 

例如：

`<hr size="3" align="center"  width="50%"> `

引号不对，出问题

`<body bgcolor=“yellow”>`

<`body bgcolor="red">`





- `<p>`标记


- - align属性
  - 事件属性


- `<br />`单标记


- - 推荐使用


- 标题标记`<h1></h1>…<h6></h6>`
- `<hr>`标记 加入一条水平线，


- - 它具有size、color、width和noshade属性。 


- 字体标记`<font>…</font>` 
- 粗体标记`<b>…</b>`
- 斜体标记`<i>…</i>`
- 下划线标记`<u>…</u>`
- 删除线标记`<strike>…</strike>`
- `< big>…</big>`、`< small>…</small>`、`<sub>…</sub>`、`<sup>…</sup>`标记 
- `<tt></tt>`用来输出打字机风格字体的文本；
- `<cite></cite>`用来输出引用方式的字体，通常是斜体；
- `<em></em>`用来输出需要强调的文本(通常是斜体加黑体)；
- `<strong></strong>`则用来输出加重文本(通常也是斜体加黑体)。

例如：

`<b><font face="宋体" size="3" color="#0000FF"><i><u>字体标记一</u></i></font></b>`



```html
<html> <head>   <title>文本标志的综合示例</title> </head> <body text="blue">
    <h1>最大的标题</h1>
    <h3>使用h3的标题</h3>
    <h6>最小的标题</h6>
    <p><b>黑体字文本</b> </p>
    <p><i>斜体字文本</i> </p>
    <p><u>下加一划线文本</u> </p>
    <p><tt>打字机风格的文本</tt></p>
    <p><cite>引用方式的文本</cite></p>
    <p><em>强调的文本</em></p>
    <p><strong>加重的文本</strong></p>
    <p><font size="-1" color="red">size取值"-1"、color取值"red"时的文本</font></p>
    <p><font size="" color="red">size取值缺省、color取值"red"时的文本</font></p>
    <p><font size="+1" color="red">size取值"+1"、color取值"red"时的文本</font></p>
</body>
</html> 
```

![](https://ww1.sinaimg.cn/large/006y8lVajw1fbg3qhirivj30aa0a93z7.jpg)

HTML字符实体

![](https://ww1.sinaimg.cn/large/006y8lVajw1fbg1bfz1j9j30dv090aay.jpg)

# 5 HTML超链接 ★

- 一般形式标记


- - `<a>`

`<a href="http://www.cnta.com/" title="中国旅游网" target="_blank">  主要旅游网</a>`

`<a><img></a>`

- `<a>`标记属性


- - target属性，定义超链接打开的目标窗口
  -  title属性，属性值为一字符串，鼠标指向超链接时，鼠标右下角显示标题文本


- 定义书签

`<a name="name">书签文本</a> `

`<a href="url#name " >…</a>`





# **6 HTML**表格 ★★

表在页面结构中的作用

- 网页结构的布局手段：表、框架
- 表格是网页的基石，可创建复杂有效页面结构
- 表格能够完全控制页面及其元素

表与框架

- 表和框架都可以构造网页的布局结构
- 表可以很容易地为页面加书签或添加到收藏夹，框架组合页面则不可以。
- 表布局结构在垂直或水平滚动时，页面所有内容滚动；框架布局允许创建彼此独立的页面区域。



# 7  HTML框架 ★

- 网页结构的布局手段：表、框架
- 增加网页的可读性、可用性
- 在框架中，可以创建彼此独立移动的页面区域，表格实现不了该功能。
- 框架可以组合静态信息和动态信息
- `<frame>`，它是一个单标记。
- `<frame>`标记定义在每一个链接内显示的内容，它必须存在于`<frameset>`标记中。
- 一个`<frameset>`标记中可以包含多个`<frame>`标记  



- ①`<frameset>`标记必须紧跟`</head>`标记之后，也就是说一个HTML文件中如果包含框架组合的话，其说明的位置必须在HTML文件的头部说明之后，而且必须在`<body>`标记之前。
- ②`<frameset>`标记中必须指定rows属性或cols属性，但这两个属性不能同时指定。
- NOFRAME: 必须使用BODY标记符。



# 8 表单（form ) ★



-  功能


- - 人机交互


- 主要标记


- - 表单标记`<form>…</form>`


- - - text单行文本框控件
    - Password
    - `<textarea> `
    - Button
    - Radio
    - Checkbox
    - `<select> …</select>`和`<option> `
    - image 
    - Hidden
    - File
    - submit/reset



## 表单标记`<Form>…</form>`	

-  功能


- - 用来标记一个表单，即定义表单的开始和结束位置 


-  属性


- - name属性，给出表单的名称，常常用于脚本编程 
  - action属性，action的值是表单处理程序的网络路径和程序名
  - method属性，method属性用来定义服务器表单处理程序从表单中获得信息的方式


- - - get方法，将数据打包放置在环境变量QUERY_STRING中作为URL整体的一部分传递给服务器 
    - POST方法，分离地传递数据给服务器表单处理程序，不需要设置QUERY_STRING环境变量，有更好的安全性，表单中数据的多少是任意的


- - target属性，target属性用来指定目标窗口或目标帧 

## 输入控件类型标记`<input type="">`

-  功能


- - 用来定义用户输入区，无尾标注。
  - 一般形式是：

 `<input type="" name = "" value="" …>`

-  属性


- -  type属性，给出控件的类型，常用的类型有：


- - - text，TEXTAREA， Radio,Checkbox, Button。`<SELECT> `  `<OPTION>`，Image, Hidden, Password,, File Submit/Reset。


- - name属性，name属性给出输入控件的名字
  - value属性，保存用户的输入和选择，服务器就是通过调用输入区域的value属性值来获得该区域的数据

# 9 HTML的扩展

缺陷：

- ⑴ 文本格式的局限 


- - 没有显式的布局和定位控制         
  - CSS。


- ⑵ 缺乏对布局控制的能力 


- - 借助表格来实现近似的效果，但对开发者的要求比较高，而且过程非常繁琐。  
  - CSS


- ⑶ 无法动态改变页面内容 


- - DHTML。


- ⑷ 交互困难 虽然配合脚本语言和CSS，HTML可以提供一定的交互能力，但这种交互能力的功能有限。
- ⑸ 适应性差 


- - 不能适应越来越多的网络设备和应用的需要，比如手机、PDA、智能家电都不能直接显示HTML。
  - wap网页使用WML，无线[标记语言](http://zhidao.baidu.com/search?word=%E6%A0%87%E8%AE%B0%E8%AF%AD%E8%A8%80&fr=qb_search_exp&ie=utf8)


- - - 2007年，Android发布以后，出现了明显的区分：即智能手机支持XHTML，而功能手机支持WML

1．动态HTML      DHTML

- HTML融入了CSS，脚本语言等技术它由三部分组成，


- - DOM（文本对象模型）


- - - DOM为网页定义了各种元素对象，使这些元素成为可以控制的对象，这是实现动态HTML的物质基础；


- - CSS（层叠样式表）


- - - CSS是对DOM中所定义的对象效果的描述，即对各种对象不同状态的描述，这是实现动态HTML目标的描述；


- - Script（脚本语言，比如VBScript和JavaScript）。


- - - Script把各种对象动态地赋予各种属性工具，是实现动态HTML的手段。

2．XML

- “Extensible Markup Language”的缩写，即可扩展标记语言。
- XML也是基于SGML的。
- 它是一种元标记语言，也就是说，在XML中，开发者可以根据自己的需要定义自己的标记，只要这种标记是满足XML命名规则的。换句话说，XML是一种能创造其他语言的语言。
- XML的更重要的作用在于它可以表示结构化的数据，从而有利于数据交换。



3．XHTML

- “eXtensible HyperText Markup Language”，即可扩展超文本标记语言。
- 是一种使用XML语法对HTML重新阐述的语言。
- XHTML 1.0  兼容 HTML 4.0。
- 优势 


- - ⑴ XHTML能够在多种网络设备和智能终端上运行，实现了数据与展示的分离。
  - ⑵ XHTML非常严谨。由于早期的HTML允许各种私有标记，所以在使用HTML开发完网页后，必须在多种浏览器环境下进行测试。而XHTML的语法是严格定义的，因此避免这种状况的发生。
  - ⑶ XML是Web发展的趋势，但目前支持原始XML数据的浏览器还不是很多，而XHTML适用于多种浏览器。
  - ​	⑷ XHTML能与其他基于XML的标记语言、应用程序和协议进行良好的交互工作。
  - ⑸ XHTML是Web标准的一部分，能很好地运行在无线设备等用户代理上。
  - ⑹ XHTML比HTML有更好的一致性，所以很少会产生功能和显示的问题  



- XHTML是一个基于XML的[标记语言](http://baike.baidu.com/view/329009.htm)，看起来与HTML有些相象，只有一些小的但重要的区别，
- XHTML就是一个扮演着类似HTML的角色的XML
- HTML语言的[语法](http://baike.baidu.com/view/135635.htm)松散，处理起来就困难(手机),因此产生了由[DTD](http://baike.baidu.com/view/147436.htm)定义规则，[语法](http://baike.baidu.com/view/135635.htm)要求更加严格的XHTML
- 文档必须是良构的，所有[标签](http://baike.baidu.com/view/135267.htm)必须闭合，也就是说开始[标签](http://baike.baidu.com/view/135267.htm)要有相应的结束[标签](http://baike.baidu.com/view/135267.htm)。另外，XHTML中所有的[标签](http://baike.baidu.com/view/135267.htm)必须小写。


- - `<br />`



4．其他标记语言

- ⑴ UIML：用户界面标记语言，一种界面描述语言
- ⑵ XForm：这种标记语言的目的在于将界面元素的展示与内容分离，这样会带来诸如软件复用性增强、更好的跨平台等优势。
- ⑶ XIML：扩展界面标记语言，它侧重于对不同应用程序间交互数据的描述，它比XML描述的数据更具体，更有针对性。
- ⑷ XAML：可扩展应用程序标记语言，它主要用于页面中文本、图象、控件等元素的布局。