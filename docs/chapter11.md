<h1>第**11**章 **HTML Head**与**Metadata**、**Cookies**</h1>



# 1 HTML头部信息

```
<base>
href用于设置默认网址的路径，
target用于设置超链接的打开方式。
<base href="http://www.google.com" target="_blank" /> 
<link>
<link rel="stylesheet" type="text/css" href="images/css.css" />
<title>、<style>和<script>
<meta>
```

# 2  Metadata元信息 ★★

Metadata: 元数据
描述数据的数据
Metadata可以描述的信息
页面的作者、完成的时间、关于页面被搜索的信息、页面所使用的字符集等等。
Metadata的内容对用户是不可见的
元数据不会显示在页面上，但是对于机器是可读的
元数据可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。

```
1.<Meta>标记\
<head>
…..
</head>
<body>
……
</body>
2.metadata属性

meta属性
Name
http-equiv
content
使用
<META NAME=“nameValue” CONTENT=“contentValue”>
<META http-equiv=“nameValue” CONTENT=“contentValue”>
 1️⃣ name属性：用于不响应HTTP头的信息类型，信息值不被加入到HTTP头中，但仍然保留在HTML文档中。
 2️⃣HTTP头 (header) 是服务器以 HTTP 传 HTML 资料到浏览器前所送出的字串，在标头 与 HTML 文件之间尚需空一行分隔。
  传统的标头一定包含下面三种标头之一，并只能出现一次。
  Content-Type: xxxx/yyyy　　
  Location: xxxx:yyyy/zzzz
  Status: nnn xxxxxx
  
  
3️⃣网页作者 author
   <meta name=“author" content=“lyunc">
4️⃣关键字 keywords
   <meta name=“keywords” content=“xml,car">

META标记符允许大多数搜索引擎并不是所有搜索引擎通过该标记符找到该网站-keywords关键词。
一个关键字<=1000字符，忽略255字符后的内容
选择和网站相关的关键字
使用关键字的单数、复数以及其他变体
不要使用冠词、介词和连结词等

5️⃣字符集选择    content-type
     <meta http-equiv=“content-type” content=“text/html; GB2312”>

6️⃣在指定时间后, 页面跳转  refresh
     <meta http-equiv=“refresh” 
     content=“20; URL=www.sina.com.cn”>
7️⃣控制浏览器的页cache  pragma
     <meta http-equiv=“pragma” 
      content=“no-cache”>

8️⃣网页有效期  expires
      <meta http-equiv=“expires” 
      content=“Fri, 8,Aug,2012 08:23:41 GMT”>
```

## Webapp  ★

- 针对Iphone、[**Android**](http://lib.csdn.net/base/15)优化后的web站点
- Iphone、Android内置浏览器都是基于webkit内核


- - `<*meta* name="renderer" content="*webkit*">` 


- - - 页面在android中显示的自适应
    - <meta content=”width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0;” name=”viewport” /> 
    - 强制让文档的宽度与设备的宽度保持1:1，并且文档最大的宽度比例是1.0，且不允许用户点击屏幕放大浏览；


- - iphone设备中的safari私有meta标签

  - - 它表示：允许全屏模式浏览
    - `<meta content=”yes” name=”apple-mobile-web-app-capable” /> `
    - ​
    - 指定的iphone中safari顶端的状态条的样式；
    - `<meta content=”black” name=”apple-mobile-web-app-status-bar-style” />` 

  - 格式

  - - 告诉设备忽略将页面中的数字识别为电话号码。
    - 解决**iOS 4.3**版本中**safari**对页面中**5**位数字的自动识别和自动添加样式
    - `<meta content=”telephone=no” name=”format-detection” />` 

# 3 cookies ★★

- 小文本文件
-  服务器在HTTP响应头中发送给用户浏览器
-  维持客户端与服务器端的状态
-  保存在客户端的一个目录中


- Cookies不能搜集所在计算机上的用户名和密码
- Cookies不能从所在的计算机中读文件
- Cookies作为文本文件，是不可执行的
- 每个Cookie中的信息只能发送给它关联的服务器

## 读写Cookies ★

- 写Cookies


- - 静态网页


- - - `<meta>`


- - 动态生成


- - - javascript
    - PHP 

- 读取Cookies


- - 动态网页PHP 
  - Session机制

Set-Cookie: name=value; expires=date; path=path; domain=domain; secure

允许多个Cookie



js:

```js
document.cookie  名字，有效期

function setCookie(c_name,value,expiredays)
{
var exdate=new Date()
exdate.setDate(exdate.getDate()+expiredays)
document.cookie=c_name+ "=" +escape(value)+
((expiredays==null) ? "" : ";expires="+exdate.toGMTString())
}
```

php:

```php
header()函数 或者 setcookie() 函数
<?php 
setcookie("user", "Alex", time()+3600);
?>
<html>
	<body>
	</body>
</html>
注意：setcookie() 函数必须位于 <html> 标签之前。
```

header()函数写：

```
标头 (header) 是服务器以 HTTP 传 HTML 资料到浏览器前所送出的字串，在标头 与 HTML 文件之间尚需空一行分隔。
传统的标头一定包含下面三种标头之一，并只能出现一次。  　　
Content-Type: xxxx/yyyy  　
Location: xxxx:yyyy/zzzz  　　
Status: nnn xxxxxx
```

- 使浏览器重定向到 PHP 的官方网站。 

```php
<?php 
header(“Location: http://www.php.net”;);  exit;  ？> 
       
       
<?php
if(xxx)
{Header("Location:http://www.php.net"); 
}
else
{    Header("Location:http://www.php2.net");
}
?>
       
       
<?php
header("refresh:3;url=http://axgle.za.net");
print('正在加载，请稍等...<br>三秒后自动跳转~~~');
?> 
```

- 让使用者的浏览器出现找不到档案的信息。 
  `header("Status: 404 Not Found"); `
- 让使用者下载档案。 
  `header("Content-type: application/x-gzip"); `
  `header("Content-Disposition: attachment; filename=文件名\"); `
  `header("Content-Description: PHP3 Generated Data"); 　　?> `


- 要使用者每次都能得到最新的资料，而不是 Proxy 或 cache 中的资料，可以使用下列的标头 
  - header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); 
  - header("Last-Modified: " . gmdate("D, d M Y H:i:s") . "GMT"); 
  - header("Cache-Control: no-cache, must-revalidate"); 
  - header("Pragma: no-cache"); 



读取cookies：



```js
Javascript  运行
PHP 
echo $_COOKIE["user"];
<?php 
if (isset($_COOKIE["user"])) 
     echo "Welcome " . $_COOKIE["user"] . "!<br />"; 
else 
     echo "Welcome guest!<br />"; ?> 
```

# 13.8 javascript 应用

```html
<html>
    <head>
         <script type="text/javascript">
              function getCookie(c_name)
                  {
                     if (document.cookie.length>0)
                        {
                         c_start=document.cookie.indexOf(c_name + "=")
                         if (c_start!=-1)
                                { 
                                   c_start=c_start + c_name.length+1 
                                   c_end=document.cookie.indexOf(";",c_start)
                                   if (c_end==-1)
                                         c_end=document.cookie.length
                                   return unescape(document.cookie.substring(c_start,c_end))
                                  } 
                        }
                    return ""
               }
           function setCookie(c_name,value,expiredays)
{
var exdate=new Date()
exdate.setDate(exdate.getDate()+expiredays)
document.cookie=c_name+ "=" +escape(value)+
((expiredays==null) ? "" : ";expires="+exdate.toGMTString())
}

function checkCookie()
{
username=getCookie('username')
if (username!=null && username!="")
  {alert('Welcome again '+username+'!')}
else 
  {
  username=prompt('Please enter your name:',"")
  if (username!=null && username!="")
    {
    setCookie('username',username,365)
    }
  }
}
                     </script>
     </head>
     <body onLoad="checkCookie()">
     </body>
</html>
```

删除cookies：

```
使过期日期变更为过去的时间点。
<?php
 // set the expiration date to one hour ago 
setcookie("user", "", time()-3600); 
?>
```

# 19.6 会话管理：Cookie、 Session

- http协议是一种无状态的连接,要想跟踪用户的行为就必须有一个能工作于不同于页面的变量
- 在PHP中可以用cookie和session两种办法实现。 


- - cookie机制采用的是在客户端保持状态的方案，
  - session机制采用的是在服务器端保持状态的方案



- Session 的工作机制


- - 为每个访问者创建一个唯一的 id (UID)，并基于这个 UID 来存储变量。
  - UID 存储在 cookie 中，
  - 或通过 URL 进行传导。


- - - URL重写----把session id直接附加在URL路径的后面 
    - 提交表单

  - ```php
    session_start() 函数启动会话,必须位于 <html> 标签之前
    <?php session_start(); // store session data $_SESSION['views']=1; 
    ?> 
    <html> 
      <body> 
        <?php //retrieve session data 
            echo "Pageviews=". $_SESSION['views']; 
         ?> 
      </body> 
    </html>
    ```

  - 删除session：

  - ```
    删除 session 
    unset()释放指定的 session 变量
    <?php 
    unset($_SESSION['views']); 
    ?>
    session_destroy() 函数彻底终结 session
    <?php 
    session_destroy(); 
    ?>
    ```

  - url保持连接：

  - ```
    第一个网页，发送uid
    str="<a href=/"main.php?user=".$uid."/">进入张三网站主页</a> "
    echo $str;
    第二个网页，读取uid
    Main.php
    echo $_GET[‘uid'];
    ```

  - 表单保持连接：

  - ```
    <form name=“testform” action=“/xxx”>
     <input type=“hidden”name=“jsessionid” value=“ByOK3vj”> 
       ……
    </form>

    $POST[‘jsessionid']
    ```

  - ​