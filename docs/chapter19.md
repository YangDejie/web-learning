<h1>第19章 PHP编程</h1>

# 19.1 PHP概述 ★

- PHP是英文Personal Home Page的缩写。


- - Hypertext Preprocessor


- PHP是免费的开源软件


- - [http://www.php.net](http://www.php.net/)


- PHP是跨平台的


- - PHP受到广泛支持。


- - - 诸如IIS、Apache等服务器软件都支持PHP

- 参考手册


- - ([http://www.php.net/docs.php](http://www.php.net/docs.php))

- ```
  <html>
  	<head>
  		<title>The first PHP example</title>
  	</head>
  	<body>
  		<?php
  			echo “<U>”;
  			echo “Hello World”；
  			echo “</U>”
  		?>
  	</body>
  </html>
  ```

- - PHP是服务器端脚本程序语言，用于实现数据库和网页之间的数据交互
  - PHP需要内嵌在HTML文档中。
  - PHP代码被包含在PHP标记符中


-   - - 四种 PHP的描述方法

    - ```
      <?PHP echo“Hello World!”; ?>   标准描述
      <script language=“PHP”>    标准描述
            echo “Hello World!”; 
        </script>
      <? echo“Hello World!”; ?>  
        需要php.ini设置 short_open_tag = On (缺省on)
      <% echo “Hello World!”; %>  
        需要php.ini设置 asp_tags = on (缺省off)
      ```


- - *PHP *代码区分大小写
  - *PHP*语句之间使用分号*“*；*”*分隔。
  - *PHP*使用*echo*、*print*和*printf*等命令函数输出信息


- 工作原理


- - 通过使用PHP编写的网页访问服务器时，
  - 脚本首先传给PHP引擎，
  - 在它进行处理后再将处理结果HTML文本传给Web服务器，
  - Web服务器再将HTML代码返回给相应的客户，
  - 客户端的浏览器解释HTML代码在客户端屏幕显示网页内容。


- PHP代码是在服务器端运行的，HTML代码是在客户端运行的，这就是PHP与html语言的最大区别。

# 19.2  PHP 语法

## 19.2.1  PHP数据类型

- 简单数据类型


- - 数字类型


- - - 整型数：18，O17, Ox18
    - 浮点数：


- - - - 0.1234        .123         1.23456E+5 

  - 字符串


- - - “hello,world!”

- 组合数据类型。


- - 数组
  - 类 



## 19.2.2  PHP标识符

构成规则

- ⑴ 字母、数字和下划线；
- ⑵ 标识符的长度是任意的；
- ⑶ 标识符的第一个字符必须是字母或下划线。
- 大小写敏感的
- 变量名、数组名、函数名前须要加一个美元货币符号“$” 
- 变量是不需要声明的 

## 19.2.3 变量

- 在PHP中，需要在变量名、数组名、函数名前须要加一个美元货币符号“$”。
- 在PHP中，变量是不需要声明的，
- 当该变量被访问时，返回的值和类型就是最近一次被赋给的值和类型。

  ​

![](https://ww2.sinaimg.cn/large/006tNc79jw1fbg99x9sboj307i05ojrr.jpg)

```
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>变量定义</title>
</head>
<body>
<?php 
$int_MyVar1;
$str_MyVar2="Hello World";
$dec_MyVar3=12.34;
$int_MyVar1=88.69;
echo $int_MyVar1."<br>";
echo $str_MyVar2."<br>";
echo $dec_MyVar3."<br>";
$串变量1="该版本的PHP支持中文变量";
echo $串变量1;
?>
</body>
</html>
```

![](https://ww1.sinaimg.cn/large/006tNc79jw1fbg9a746isj30io0c4wgt.jpg)

## 19.2.4 常量

- 自定义常量


- - 一般放在文档的首部
  - 常量名最好是用大写，PHP大小写敏感
  - 在.inc文件中定义常量，使用require、inlude调用



```
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>常量定义实例</title>
<?php 
	define ("SERVER", "127.0.0.1");
	define ("USERNAME","HTTPD");
	define ("PASSWORD","MyPass");
	define ("DESC_PROG","本程序采用PHP+Apache+MySQL技术");
?>
</head>
<body>
<?php
	echo SERVER."<br>";
	echo USERNAME."<br>";
	echo PASSWORD."<br>";
	echo DESC_PROG."<br>";
?>
</body>
</html>
```



- 系统定义常量


- - _FILE_ 当前解析的脚本文件名
  - _LINE_当前解析的脚本文件的当前行号
  - PHP_VERSION 当前PHP的版本号
  - PHP_OS 当前的操作系统名称
  - E_ERROR 标志最近不可恢复的错误

- ```
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=gb2312">

  <title>系统定义常量演示</title>
  </head>
  <body>
  <?php
  echo "当前文件名：".__FILE__."<br>";
  echo "当前行号：".__LINE__."<br>";
  echo "当前操作系统：".PHP_OS."<br>";
  echo "当前PHP的版本：".PHP_VERSION."<br>";
  ?>
  </body>
  </html>
  ```





## 19.2.5 运算符与表达式

- 算术操作符：+ - * / %  $a++  ++$a  $a--  --$a
- 字符串操作符： “.”


- -  $str_val="It is time"."to go to bed.";


- 比较运算符：“==” “>” “<” “!=” “>=” “<=”
- 逻辑运算符:  “and” “&&” “or” “||” “xor” “!”
- 位操作符: “&” “|” “^” “~” “<<” “>>”



```
<?php 
//连接运算符只保留一个空格
$str_str1="Every dog      "."   has its day.";
echo $str_str1."<br>";

//连接运算符还可以起到类型转换的作用
$dec_var1=15.3;
$str_str2="He has ".$dec_var1." pounds.";
echo $str_str2."<br>";
?>
```

```
<?php 
$var=5+"10.7";
echo $var."<br>"; 
$var=5+"10.2e3";
echo $var."<br>"; 
$var=5+"abc1.0e3";
echo $var."<br>"; 
$var=5+"3.3+15";
echo $var."<br>";   ?>
```

##  19.2.6 **** PHP**的注释方式



![](https://ww1.sinaimg.cn/large/006tNc79jw1fbg9cz8pdjj30a50ar3zd.jpg)

##  19.2.7 函数

- 函数是用来实现某种特定功能的并可以重复调用的一段代码
- 保留函数


- - I/O函数
  - 数据函数
  - 数学函数
  - 时间函数
  - 数据库函数
  - 执行外部程序的函数：exec、system
  - 退出函数：exit


- 自定义函数

- ```
  <?php 
  define ("PI",3.14);
  function circle_area($diameter)
  {
  	$area=PI*$diameter*$diameter/4;
  	return $area;
  }
  ?>
  ```


  <?php 
  	$int_circle_diameter=10;
  	echo "直径为".$int_circle_diameter."的圆面积是".circle_area($int_circle_diameter);
  ?>
  ```

## 19.2.8、数组

- PHP中可以用字符串表示数组元素的下标
- 赋值


- - 使用array函数


- - - *$PHPTeam=array("John","Tom","Adam","Bob");*
    - *$my_friends=array("best"=>"*武钢*","good"=>"*李楠*","*王莉娜*")*
    - *$student=array(*

*		"team1"=>array( "Bill","Tom","Chris"),*

*		"team2"=>array("Jason","Mary","May")*

*		);*

- - 引用数组时，既可以使用定义的下标引用，也可以使用数字下标引用

- ```
  使用array函数
  $PHPTeam=array("John","Tom","Adam","Bob");
  依次对数组元素赋值
  $PHPTeam[0]= "John";
  $PHPTeam[1]= "Tom";
  $PHPTeam[2]= "Adam";
  $PHPTeam[3]= "Bob";
  循环赋值
  	for($counter=0;$counter<=10; $counter++)
  		$arraySample[$counter]= $counter+2;
  ```



##  19.2.9、类

```
<body>
<?php
class Vehicle{
var $speed;
function accelerate($num)
{
    if ($this->speed+$num<150)
    {
	$this->speed+=$num;
	echo $this->speed;
	echo "<br>";
    }
    else
   {
	$this->speed=150;
	echo $this->speed;
	echo "<br>";
   }
}
function decelerate($num)
{
    if ($this->speed>$num)
     {$this->speed-=$num;}
    else
      {return 0;
    }
}
}
$vehicle=new Vehicle;
$vehicle->accelerate(45);
$vehicle->accelerate(45);
$vehicle->accelerate(45);
$vehicle->accelerate(45);
$vehicle->accelerate(45);
?>
</body>
```

# 19．3 PHP控制结构

- if, else, elseif,    特殊判断
- ?:运算符
- switch跳转语句
- while、do … while 和 for 循环
- break、continue

```
<?php 
$str_name="王刚";
if ($str_name=="王刚")
{
$log_enter_allow=true;
echo "欢迎".$str_name."浏览该网页"."<br>";
}
else
{
$log_enter_allow=false;
echo "请注册后再登入";
}
?>
```

# 19.4 PHP与WEB页面的交互 ★★

## 输出函数  

I/O函数：输出函数

- 包括print()、printf()和echo。
- print()是最简单的输出函数，它直接将参数发送给浏览器；
- printf()用于格式输出
- echo是早期的PHP版本中用来做输出的，它的特殊之处在于不需要括号

```
<?php 
print  "显示一个字符串";//不使用括号
print '<br>';
print  ("显示一个字符串");//使用括号
print '<br>';

//print可以在for循环中，echo 则不可以
for ($i=1,$j=1;$i<4;$i++,print "<br>")
{
	$j+=$i+$j;
	echo "$i $j";
}
?>


<table cellpadding="10" cellspacing="0" border=1> 
	<tr><td> 直径</td>
		<td> 圆的面积</td></tr>
	<tr>
 		<td>
			<?php  $int_circle_diameter=10;
			echo $int_circle_diameter;?>
		</td>
		<td>
			<?php echo circle_area($int_circle_diameter);?>
 		</td>
	</tr>
</table>
```



## 图像输出

- PHP提供了一些内置的图像信息函数
- GD库提供了一系列用来处理图片的API，


- - 处理图片，或者生成图片。


- GD库是一个开放的、源代码公开的函数库[http://www.boutell.com/gd](http://www.boutell.com/gd)）。
- 目前，GD2库支持JPEG、 PNG和WBMP等多种图像格式。


- 配置


- - 在windows环境下，找到php.ini文件，去除 "；extension=php_gd2.dll"前面的分号，重启Apache就可以了。
  - 在Linux环境下，扩展中添加extensiongd2.so即可


- 创建画布


- - *Resource imagecreate(int x_size, int y_size);   *


- 分配颜色


- - *int imagecolorallocate ( resource image, int red, int green, int blue)*；


- 在背景上绘制图像轮廓或输入文本。
- 输出最终图形


- - Imagecreatefromjpeg（resource image）打开jpg格式图片。 
  - Imagecreatefromgif（resource image）打开gif格式图片。 
  - Imagecreatefrompng（resource image）打开png格式图片。
  - Imagecreatefromgd（resource image）打开gd生成的图片 


- 释放资源 


- - imagedestroy(resource image）函数释放资源



```
<?php
$img = imagecreate(200, 200); 
$bg = imagecolorallocate($img, 12,135, 20);            
$white = imagecolorallocate($img, 255, 255, 255);       
imagearc($img, 100, 100, 150, 150, 0, 360, $white);//绘制白色的圆  
imagepng($img);                                      
imagedestroy($img);                                   
?>
```



## WEB页面布局

- 通过文件包含语句，可以设计网页的布局
- 文件包含是指将另一个文件的内容包含到当前文件中来。


- - 使用文件包含可以减少代码的重用性
  - PHP提供include语句，require语句，include_once语句和require_once语句


- 文件包含可以用于创建可在多个页面重复使用的函数、页眉、页脚或元素

```
include语句
一般放在流程控制的处理区段中
每次调用时都要重新计算一遍
错误：Include语句会生成一个警告（但是脚本会继续执行）
include受条件限制
include在一个if中，如果if条件不成立文件将不会被包含进来，
如果文件不存在，错误为警告，程序继续执行
```

```
Require语句
用指定的文件替代自身，成为程序的一部分
只在它第一次出现时，就已经被相应文件所代替了，不会考虑在这以后该文件内容是否发生变化
通常放在程序的最前面，PHP程序在执行前，就会读入相应的文件
错误：require语句会生成一个致命错误（fatal error）（在错误发生后脚本会停止执行）。
如果文件不存在，为至命错误程序终止 
```

```
<html>  
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>include引用文件</title>
</head>
<body>
<?php
include "sample-2003-1.php";
echo "<br>";
echo "Hello World ! ";  
?>
</body>
</html>
```

```
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>include引用文件</title>
</head>
<body>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>显示当前文件名和行号</title>
</head>
<body>
c:\csnews\php-test\sample-2003-1.php<br>17</body>
</html>
<br>Hello World ! </body>
</html>
```



## 表单元素的获取方法

```
<form action="welcome.php" method="get">
Name: <input type="text" name="name" /><br>
Age: <input type="text" name="age" /><br>
<input type="submit" />
</form>
```



- 当用户填写该表单并单击提交按钮时，表单的数据会被送往 "welcome.php" 这个文件。

##Get  post


- - $_GET 变量，

  - - 用于收集来自 method="get" 的表单中的值。
    - $_GET 变量是一个数组，
    - 内容是由 HTTP GET 方法发送的变量名称和值。

  - $_POST 变量，

  - - 用于收集来自 method="post" 的表单中的值
    - $_POST 变量是一个数组
    - 内容是由 HTTP POST 方法发送的变量名称和值。


```
<form action="welcome.php" method=“get">
	Name: <input type="text" name="name" /><br>
	Age: <input type="text" name="age" /><br>
	<input type="submit" />
</form>

<body>
	Welcome <?php echo $_GET["name"]; ?>.<br />
	You are <?php echo $_GET["age"]; ?> years old!
</body>

注意浏览器的地址栏，可以清晰的看到用户输入的信息
```

```
从带有 POST 方法的表单发送的信息，对任何人都是不可见的
<body>
Welcome <?php echo $_POST["name"]; ?>.<br />
You are <?php echo $_POST["age"]; ?> years old.
</body>
```

```
$_REQUEST 变量包含了 $_GET, $_POST 以及 $_COOKIE 的内容。
可用来取得通过 GET 和 POST 方法发送的表单数据的结果。
<body>
Welcome <?php echo $_REQUEST["name"]; ?>.<br />
You are <?php echo $_REQUEST["age"]; ?> years old!
</body>
输出结果和POST方式相同
```



## 通过URL 传递数据

```
<body>
	<a href="main.php?user=three">进入张三网站主页</a>
	<a href="main.php?user=four">进入李四网站主页</a>
</body>

<?php 
	echo $_GET['user'];
?>
```



- 会话管理：Cookie、Session