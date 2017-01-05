<h1>第22章 PHP MySQL ODBC接口动态网页设计</h1>

# 1.PHP通过ODBC访问MySQL数据库的步骤

1. **创建ODBC数据源**
2. **建立与数据库的连接**
3. **执行SQL语句**
4. **存储、处理并显示操作结果数据**
5. **释放结果集所占资源**
6. **关闭数据库的连接**

# 2.通过ODBC对数据库的连结与关闭

- **非永久性连接：**

 int odbc_connect(数据源名,用户名,口令,游标类型);**

- **非永久性连接关闭**

  int odbc_close(连接句柄);**

  int odbc_close_all(void);**

- **永久性连接：**

  int odbc_pconnect(数据源名,用户名,口令,游标类型);**

# 3.建立系统DSN(1)

# 4.PHP-ODBC连接数据库的方法

- **格式1：PHP直接向ODBC发送SQL,并立刻执行**

int odbc_do(连接句柄,查询语句);

​	或

int odbc_exec(连接句柄,查询语句);

- **格式2：PHP先向ODBC发送SQL,得到命令后再执行**

int odbc_prepare(连接句柄,查询语句);

  int odbc_execute(prepare_id,[参数数组]);



4.PHP-ODBC连接数据库的方法(实例)

```
<body>
<?php 
$db="odbc_db";
$user="root";
$passwd="your_password";
$db_id=odbc_pconnect($db,$user,$passwd,SQL_CUR_USE_ODBC);
$odbc_query="select user,password from user";
$odbc_pre=odbc_prepare($db_id,$odbc_query);
$odbc_run=odbc_execute($odbc_pre);
if(!$odbc_run){
	echo "ODBC连接数据库失败！";
	exit;
}
else {
	echo "ODBC连接数据库成功！";
}
?>
</body>
```

# 5.通过ODBC获取数据记录和字段的方法

```
制定序号的记录存于一个数组
    格式：int odbc_fetch_into(int result_id,
          int [rownumber],array result_array);
每次读一条记录
    格式：int odbc_fetch_row(int result_id, 
          int[rownumber])
从结果集中度去某一个字段的值
    格式：int odbc_result(int result_id, 
          mixed field);
获取查询结果集中的记录数
    格式：int odbc_num_rows(int result_id);
获取指定字段的字段名称
   格式：string odbc_fieldname(int result_id,
           int field_number);
获取指定字段的数据类型
   格式：string odbc_field_type(int result_id,
           int field_number);
获取指定字段的长度
   格式：string odbc_field_len(int result_id,
           int field_number);
```

```
<?php 

$db=“odbc_library”;//已建立library数据库的数据源
$user="root";
$passwd="your_password";
$db_id=odbc_pconnect($db,$user,$passwd,SQL_CUR_USE_ODBC);
$odbc_query="select id,cs_name,sex from cs_students";
$odbc_pre=odbc_prepare($db_id,$odbc_query);
$res_id=odbc_execute($odbc_pre);
if(!$res_id){
	echo "ODBC连接数据库失败！";
	exit;
}
echo "ODBC连接数据库成功！";
echo odbc_num_rows($odbc_pre)."<br>";
while (odbc_fetch_row($odbc_pre)) {
	$str_id=odbc_result($odbc_pre,1);
	$str_cs_name=odbc_result($odbc_pre,2);
	$str_sex=odbc_result($odbc_pre,3);
	echo "<br>";
	echo "学号：".$str_id."　";
	echo "姓名：".$str_cs_name."　";
	echo "性别：".$str_sex;
	echo "<br>";
}
odbc_close($db_id);
?>
```


# 6.ODBC数据库其他常用函数


- 提交

   格式：**int odbc_commit(int connection_id);**

- 自动提交

   格式：**int odbc_autocommit(int connection_id,**

                     int [OnOff])

- 取消操作

   格式：**int odbc_rollback(int connection_id);**

- 释放资源

   格式：**int odbc_free_result(int result_id);**