<h1>第**15**章 **Ajax**设计方法</h1>

# 15.1 什么是Ajax ★

- Ajax的全称是：Asynchronous异步JavaScript+XML 
- Ajax不是一个技术，它实际上是几种技术，每种技术都有其独特之处，合在一起就成了一个功能强大的新技术。 
- Web开发领域的最新时髦术语其实质是“旧貌换新颜”
- Ajax可以让开发人员构建基于Java技术的Web应用，并打破了使用页面重载的惯例
- 通过在后台与服务器进行少量数据交换，AJAX 可以使网页实现异步更新。
- 在不重新加载整个网页的情况下，对网页的某部分进行更新。 
- 实例


- - http://www.w3school.com.cn/ajax/ajax_asp_php.asp

Ajax包括： 

- HTML 用于建立 Web 表单并确定应用程序其他部分使用的字段。 
- JavaScript 代码是运行 Ajax 应用程序的核心代码，帮助改进与服务器应用程序的通信。


- - 使用XMLHttpRequest对象进行异步数据接收 


- DHTML 或 Dynamic HTML，用于动态更新表单。使用 div、span 和其他动态 HTML 元素来标记 HTML。 
- 文档对象模型 DOM 用于（通过 JavaScript 代码）处理 HTML 结构和（某些情况下）服务器返回的 XML

# 15.2 Ajax工作原理 ★

![](https://ww2.sinaimg.cn/large/006tNc79jw1fbg8jmqew8j308d09vdg5.jpg)

- Ajax用来描述一组技术，它使浏览器可以为用户提供更为自然的浏览体验。
- ​
- 最重要的是，用户甚至不知道浏览器正在与服务器通信：Web站点看起来是即时响应的。
- ​
- 在Ajax之前，Web站点强制用户进入提交/等待/重新显示内容，用户的动作总是与服务器的“思考时间”同步。
- ​
- Ajax提供与服务器异步通信的能力，从而使用户从请求/响应的循环中解脱出来。
- 在面向消费者的诸多应用当中，Google的Gmail和GoogleMaps就是最常见的例子。在Gmail当中，AJAX负责如何开启线程会话，以显示不同邮件的文本内容。而在Maps当中，AJAX允许用户以一种似乎无缝的方式拖拉及滚动地图。 
  还有雅虎的Flickr像片共享应用和亚马逊网站的A9搜索引擎。
  这些UI都充分地使用了后台通道
- 不过AJAX应用软件的适用领域具有一定的局限性。因为它们利用了一些最新的Web技术，所以只能在某些Web浏览器里面运行 
- Ajax的核心是JavaScript对象XmlHttpRequest。该对象在Internet Explorer 5中首次引入

# 17.3 XMLHttpRequest 对象★

- XMLHttpRequest是一个 JavaScript 对象，处理所有服务器通信的对象。
- 一个Ajax交互从一个XMLHttpRequest对象开始。
- 它允许一个客户端脚本来执行HTTP请求，并且将会解析一个XML格式的服务器响应。
- ​

1)启动一个Ajax过程  form+ JavaScript

```
<form>
	City: 
	<input type="text" name="city" id="city" size="25"               
                       onChange="callServer();" />
    State: 
	<input type="text" name="state" id="state" size="25" 
                     onChange="callServer();" />
	Zip Code: 
	<input type="text" name="zipCode" id="city" size="5" />
</form>
```



2)创建一个XMLHttpRequest实例

- 所有现代浏览器均支持 XMLHttpRequest 对象


- - IE7+、Firefox、Chrome、Safari 以及 Opera


- - - variable=new XMLHttpRequest();


- - IE5 和 IE6 使用 ActiveXObject


- - - variable=new ActiveXObject("Microsoft.XMLHTTP");

```
IE中安装的 JavaScript 技术版本不同，MSXML 实际上有两种不同的版本
var xmlHttp = false;
	try {xmlHttp = new ActiveXObject("Msxml2.XMLHTTP");} 
	catch (e) 
		{ try {
            xmlHttp = new ActiveXObject("Microsoft.XMLHTTP"); } 
		  catch (e2) {    xmlHttp = false;  }
	  }
xmlHttp是XMLHttpRequest句柄
```



3)获取表单数据 。

```
function callServer() {
  var city = document.getElementById("city").value;
  var state =document.getElementById("state").value;
   if ((city == null) || (city == "")) return;
   if ((state == null) || (state == "")) return;
  // 建立URL，escape 函数是一个顶级 JavaScript 函数，可将属性值添加到URL中
  var url = "/scripts/getZipCode.php?city=" + escape(city) + "&state=" + escape(state);
```



4)将目标URL设置到XMLHttpRequest对象上。 

5)发送请求

```
 // 打开一个与服务器的连接
  xmlHttp.open("GET", url, true);
  // 设置结束后服务器运行的函数名
  xmlHttp.onreadystatechange = updatePage;
  // 发送这个请求
  xmlHttp.send(null);
}
```

XMLHttpRequest 对象的 open() 方法

```
指定了连接方法（GET）
与 POST 相比，GET 更简单也更快，并且在大部分情况下都能用。
和要连接的 URL。
最后一个参数
如果设为 true，那么将请求一个异步连接（这就是 Ajax 的由来）
如果设为 true，当服务器在后台处理请求的时候用户仍然可以使用表单（甚至调用其他 JavaScript 方法）。 。
如果使用 false，那么代码发出请求后将等待服务器返回的响应。
```

- 方法


- - **open()**


- - - 初始化 HTTP 请求参数,但是并不发送请求。


- - **send()**
  - 发送 HTTP 请求，使用传递给 open() 方法的参数，以及传递给该方法的可选请求体。


- 事件句柄


- - **onreadystatechange**：
  - 每次 readyState 属性改变的时候调用的事件句柄函数。

异步操作，等待服务器端响应

等待。。。。。。

6)处理服务器响应 

```
function updatePage() 
{
  if (xmlHttp.readyState = = 4) {
    var response = xmlHttp.responseText;
    document.setElementById("zipCode").value = response;
  }
}
```

- **readyState**


- - HTTP 请求的状态. 5 个状态
  - 当一个 XMLHttpRequest 初次创建时，这个属性的值从 0 开始，直到接收到完整的 HTTP 响应，这个值增加到 4。


- **responseText **属性


- - 获得字符串形式的响应数据


- **responseXML **属性


- - 来自服务器的响应是 XML，而且需要作为 XML 对象进行解析



# 19.6 PHP与Ajax ★

- PHP处理XML   不完全AJAX

- ![](https://ww4.sinaimg.cn/large/006tNc79jw1fbg8p7o1fqj307w08z0th.jpg)

- ![](https://ww2.sinaimg.cn/large/006tNc79jw1fbg8pc07omj309506aglv.jpg)

- ```
  <?php
  $q=$_GET["q"];
  $xmlDoc = new DOMDocument();
  $xmlDoc->load("cd_catalog.xml");
  $x=$xmlDoc>getElementsByTagName('ARTIST');
  	返回所有具有指定名称的元素节点。
  for ($i=0; $i<=$x->length-1; $i++)
  { if ($x->item($i)->nodeType==1)
   { if ($x->item($i)->childNodes->item(0)->nodeValue
   == $q)
      { $y=($x->item($i)->parentNode);} }
  }
  $cd=($y->childNodes);
  for ($i=0;$i<$cd->length;$i++)
  { 
  if ($cd->item($i)->nodeType==1)
    { echo($cd->item($i)->nodeName);
    echo(": ");
    echo($cd->item($i)->childNodes->item(0)->nodeValue);
    echo("<br />");
    } 
  }
  ?>
  ```

- **responseXML**

- - - 对请求的响应，解析为 XML 并作为 Document 对象返回

  - 过程

  - - 1)启动一个Ajax过程  form+ JavaScript


- - 2)创建一个XMLHttpRequest实例
  - 3)获取表单数据 。
  - 4)将目标URL设置到XMLHttpRequest对象上。 
  - 5)发送请求
  - 6)处理服务器响应 

4)将目标URL设置到XMLHttpRequest对象上。 

5)发送请求

```
xmlHttp.open("GET", url, true); 
xmlHttp.open("GET", “cd_catalog.xml", true);

// 设置结束后服务器运行的函数名
  xmlHttp.onreadystatechange = updatePage;
  // 发送这个请求
  xmlHttp.send(null);
}
```

6)处理服务器响应 

```
function updatePage() 
{
  if (xmlHttp.readyState = = 4) {
    var response = xmlHttp.responseXML;
   var x=response.getElementsByTagName(“ARTIST”);
………..
  }
}
```

## 补充：JSON ★  

- **JavaScript **对象表示法


- - **JavaScript Object Notation**


- JSON 是轻量级的文本数据交换格式


- - **JSON **是存储和交换文本信息的语法。
  - 类似 **XML**。** **比 **XML **更小、更快，更易解析。


- JSON 独立于语言 


- - JSON 解析器和 JSON 库支持许多不同的编程语言。


- JSON 具有自我描述性，更易理解

```
<html>
<body>
<p>
Name: <span id="jname"></span><br />
Age: <span id="jage"></span><br />
Address: <span id="jstreet"></span><br />
Phone: <span id="jphone"></span><br />
</p>
<script type="text/javascript">
var JSONObject= {"name":"Bill Gates","street":"Fifth Avenue New York 666","age":56,"phone":"555 1234567"};
document.getElementById("jname").innerHTML=JSONObject.name
</script>

</body>
</html>
```

- JSON 是纯文本
- JSON 具有“自我描述性”（人类可读）
- JSON 具有层级结构（值中存在值）
- JSON 可通过 JavaScript 进行解析
- JSON 数据可使用 AJAX 进行传输

```
<html>
<body>
<p>
First Name: <span id="fname"></span><br /> 
Last Name: <span id="lname"></span><br /> 
</p> 
<script type="text/javascript">
var txt = '{"employees":[' +
'{"firstName":"Bill","lastName":"Gates" },' +
'{"firstName":"George","lastName":"Bush" },' +
'{"firstName":"Thomas","lastName":"Carter" }]}';
var obj = eval ("(" + txt + ")");
document.getElementById("fname").innerHTML=obj.employees[1].firstName 
document.getElementById("lname").innerHTML=obj.employees[1].lastName 
</script>
</body>
</html>
```

- **JSON - **转换为 **JavaScript **对象
- JSON 文本格式在语法上与创建 JavaScript 对象的代码相同。
- 由于这种相似性，无需解析器，JavaScript 程序能够使用内建的 [eval() 函数](http://www.w3school.com.cn/jsref/jsref_eval.asp)，用 JSON 数据来生成原生的 JavaScript 对象。

JSON与XML

- XML的优点


- - 格式统一，符合标准；
  - 容易与其他系统进行远程交互，数据共享比较方便。


- XML的缺点


- - XML文件庞大，文件格式复杂，传输占带宽
  - 服务器端和客户端都需要花费大量代码来解析XML


- - - 导致服务器端和客户端代码变得异常复杂且不易维护；
    - 客户端不同浏览器之间解析XML的方式不一致，需要重复编写很多代码；
    - 服务器端和客户端解析XML花费较多的资源和时间。


- JSON的优点：

  - 数据格式比较简单，易于读写，格式都是压缩的，占用带宽小；
  - 易于解析，客户端JavaScript可以简单的通过eval()进行JSON数据的读取；
  - 支持多种语言，包括ActionScript, C, C#, ColdFusion, Java, JavaScript, Perl, PHP, Python, Ruby等服务器端语言，便于服务器端的解析；
  - 已经有PHP-JSON和JSON-PHP出现了，偏于PHP序列化后的程序直接调用，PHP服务器端的对象、数组等能直接生成JSON格式，便于客户端的访问提取；
  - 因为JSON格式能直接为服务器端代码使用，大大简化了服务器端和客户端的代码开发量，且完成任务不变，并且易于维护。





- JSON的缺点

  - 没有XML格式这么推广的深入人心和喜用广泛，没有XML那么通用性；
  - JSON格式目前在Web Service中推广还属于初级阶段。