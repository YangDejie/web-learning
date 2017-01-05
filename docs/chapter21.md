<h1>第21章 PHP MySQL专用接口动态网页设计</h1>

**PHP访问MySQL数据库的步骤**

1. **建立与MySQL数据库服务器的连接**
2. **选择要访问的数据库**
3. **执行SQL语句**
4. **存储查询结果**
5. **显示结果数据**
6. **关闭MySQL数据库服务器的连接**





# 21.2连接与关闭

```
非永久性连接：
  int mysql_connect(string [hostname][:port],  
       string [username],string [password]);
非永久性连接关闭
  int mysql_close(连接句柄);
永久性连接：可以返回以前连接的ID;无须关闭； 
                首次建立的连接一直有效。
  int mysql_pconnect(string [hostname][:port],  
       string [username],string [password]); 
```

```
<?php 
$Server="localhost";
$user="root";
$pass="your_password";
$con=mysql_connect($Server,$user,$pass);
if (!$con)
  		{die('Could not connect ');}
……
mysql_close($con);
?>
die( status) 函数输出一条消息，并退出当前脚本。该函数是 exit() 函数的别名。参数status是必需的。规定在退出脚本之前写入的消息或状态号。
```

# 21.3 PHP对MySQL数据库操作

**步骤**

- **执行SQL语句**
- **读取存储查询结果集**
- **显示、操作结果记录数据**
- ​
- **int mysql_query(string SQL查询字串，int [连接句柄]);**
- **注释：SQL 语句对大小写不敏感。**
- **CREATE DATABASE 数据库名**
- **DROP DATABASE database_name**



```
<?php
$con = mysql_connect("localhost","root","passw");
if (mysql_query("CREATE  DATABASE  my_db",$con))
  		{ echo "Database created";}
else
 		{echo mysql_errno().":".mysql_error();}
mysql_close($con);
?>
```

```
<?php
$con = mysql_connect("localhost","root","");
if (mysql_query("DROP DATABASE my_db1",$con))
  		{ echo "Database droped";}
else
 		{echo mysql_errno().":".mysql_error();}
mysql_close($con);
?>
```

```
格式1：
  int mysql_db_query(数据库名,查询语句,连接句柄);

格式2：
  int mysql_select_db(数据库名，连接句柄);
  int mysql_query(查询语句,连接句柄);
```

- int mysql_list_dbs(连接句柄); 

返回指定连接中的所有能用的数据库名称



- **对查询结果的存储的方式有两种：**


- - **使用数组的方式**


- - - array mysql_fetch_array(结果集,结果类型);


- - **使用类的方式。**


- - - object mysql_fetch_object(结果集,结果类型);

- **辅助显示函数**


- - **Bool mysql_db_name(int list, int row, int [field]);**


- - - **必选参数list是mysql_list_dbs()函数的返回结果，是指向查询结果记录的指针；**
    - **必选参数row是规定结果集中的行号，以 0 开始**


- - **Int mysql_num_rows（int list）函数返回结果集中行的数目**

```
<?php
$con = mysql_connect("localhost", "root", "");
if (!$con)
  {die('Could not connect: ' . mysql_error());}
$db_list = mysql_list_dbs($con);
$db_count = mysql_num_rows($db_list);
echo "存在".$db_count."个数据库<br>";
$i = 0;
while ($i < $db_count) 
  {echo mysql_db_name($db_list, $i) . "<br />";
  $i++; }
 mysql_close($con);
?>
```



# 21.4 PHP对MySQL数据表操作

- **用mysql_query() 函数**


- - **CREATE TABLE table_name(column_name1 data_type,column_name2 data_type, column_name3 data_type,.......)**
  - **DROP TABLE table_name**
  - **SHOW  COLUMNS FROM 表名**
  - ​


- **查询数据表名**


- - **mysql_list_tables()和mysql_tablename()。*

```
<?php
$con = mysql_connect("localhost","root","");
if (!$con)
  		{die('Could not connect: ' . mysql_error());}
mysql_select_db("my_db", $con);
$sql = "CREATE TABLE person (Name varchar(15),Gender varchar(15),Age int)";
mysql_query($sql,$con);
mysql_close($con);
?>
```

```
<
$con = mysql_connect("localhost","root","");
if (!$con)
  		{die('Could not connect: ' . mysql_error());}
mysql_select_db("my_db", $con);
$sql = "drop TABLE teacher";
mysql_query($sql,$con);
mysql_close($con);
?>
```

```
<?php 
$con = mysql_connect("localhost","root","");
if (!$con)
{die('Could not connect: ' . mysql_error());}
$result = mysql_list_tables('my_db');
$db_count = mysql_num_rows($result);
$i = 0;
while ($i < $db_count) 
	{echo  mysql_tablename($result, $i) . "<br />";
  	$i++;}
?>
```

```
mysql_select_db("my_db", $con);
$sql = "SHOW  COLUMNS FROM person1";
$result=mysql_query($sql,$con);
while($row = mysql_fetch_array($result))
{
echo $row[0]. "\n"; 
echo $row[1]."\n"; 
echo $row[2]. "\n"; 
echo "<br>"; 
}
```

```
<?php 
$con = mysql_connect("localhost","root","");
$fields = mysql_list_fields("my_db", "stu", $con);
$columns = mysql_num_fields($fields);
for ($i = 0; $i < $columns; $i++) 
{
echo mysql_field_table($fields, $i) . "\n";
echo mysql_field_name($fields, $i) . "\n";
echo mysql_field_len($fields, $i) . "\n";
echo mysql_field_flags($fields, $i) . "\n";
echo mysql_field_type($fields, $i) . "\n";
echo "<br>";
}
?>
```

```
$sql = "SELECT * from Person";
$result = mysql_query($sql,$con);
while ($property = mysql_fetch_field($result))
{
 echo "Field name: " . $property->name . "<br />";
 echo "Table name: " . $property->table . "<br />";
```

# 21.5 PHP对MySQL记录操作

- **添加记录**


- - **INSERT INTO table_name VALUES (value1, value2,....)**

- ```
  <?php
  $con = mysql_connect("localhost","root","passw");
  if (!$con)
    {die('Could not connect: ' . mysql_error());}
  mysql_select_db("my_db", $con);
  mysql_query("INSERT INTO person (Name, Gender, Age) VALUES ('Peter', 'male', '35')");
  mysql_close($con);
  ?>	
  ```

- ​


- **删除记录**


- - **DELETE FROM table_name WHERE column_name = some_value**

- ```
  echo "<input type='checkbox' name='checkbox[]' value='"
  .$row["id"]."'>";
  ```

- ​


- **修改记录**


- - **UPDATE table_name SET column_name = new_value WHERE column_name = some_value**

- ```
  while($row = mysql_fetch_array($result))
  {
  			echo "<tr>";
  			echo "<td>" .$row["Name"]. "</td>";
  			echo "<td>" .$row["Gender"]. "</td>";
  			echo "<td>" .$row["Age"]. "</td>";
  			
  //	把记录中id作为URL参数
  			echo "<td><a href=\"update.php?id=";
  			echo $row["id"];
  			echo "\">"."修改". "</a></td>";
  			echo "</tr>";
  }
  $query="select * from person2 where id=".$_GET["id"];
  $result=mysql_query($query,$con);
  $row = mysql_fetch_array($result);
  ?>
  <form action="ok.php" method="get">
  Name: 
  <input type="text" name="Name" value=
  <?php echo $row["Name"];?>
  >

  $query="update person2  set  name='".$_GET["Name"].
  "', gender='".$_GET["Gender"]."',age='".$_GET["age"].
  "' where id='".$_GET["nid"]."'"; 
  $result=mysql_query($query,$con);
  If($result)
  	{
  	echo "<script>
  		alert('修改成功');
  		window.location.href='index.php';
  		</script>";
  	}
  else
  	{
  	echo "<script> 
  		alert('修改失败');
  		window.location.href='index.php';
  		</script>";
  	}
  ```

- ​


- **查询记录**


- - **SELECT column_name(s) FROM table_name**


- - **SELECT column_name(s) FROM table_name**
  - **对查询结果的存储的方式有两种：使用数组的方式和使用类的方式。**


- - - **数组存储格式：**

- **		 array mysql_fetch_array(结果集,结果类型);**

- - - **类存储格式：**

- **		 object mysql_fetch_object(结果集,结果类型);**


- 对查询结果的当前记录进行存储

array mysql_fetch_row(int 结果);

- 对查询结果中的某个具体的数据进行存储，

int mysql_result(int 结果,int 记录序号, mixed 字段);

- 对查询所获取的结果的总数量进行统计

array mysql_num_rows (int 结果);

- 释放查询结果所占用的内存 

boolean mysql_free_result(int result); 





```
// 用URL 传递显示的页数
if(isset($_GET['page']))
	{$page=$_GET['page'];}
Else
	{$page=1;}



if($page==1)
	{
	echo "<tr>";
	echo "<td></td>";
echo "<td></td>";
	echo "<td>" ;
	echo "<a href=\"index.php?page=".($page+1)."\">next </a>";
	echo "</td>";
	echo "<td>";
	echo "<a href=\"index.php?page=".$pagenum."\">end page </a>"; 
	echo "</td>";
	echo "</tr>";
	}
```

