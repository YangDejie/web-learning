<h1>第20章 MySQL数据库</h1>

# 20.1 MySQL概述

- **MySQL关系数据库管理系统**
- **MySQL是一种开放源码软件**
- **具有快速、可靠和易于使用**
- **结构化查询语言：SQL**
- **Web中小型数据库的首选**

# 20.2 MySQL的工作原理  C/S结构 ★

# 20.3 MySQL启动与退出 ★

- **建立到MySQL服务器的连接**

**格式：mysql [-h host_name] [-u user_name]**

**              [-pyour_password]**

**-p和your_password中间没有空格**



# 20.4  口令管理





# 20.5 数据库操作

- **查看数据库**


- - **SHOW DATABASES;**
  - **SELECT database();**


- **创建数据库**


- - **CREATE DATABASE 数据库名;**


- **删除数据库**


- - **DROP DATABASE [IF EXISTS] 数据库名;**


- **打开数据库**


- - **USE 数据库名;**

# 20.7 “表”操作

drop

alter

# 20.8 “记录”操作
- 格式1：对所有字段赋值,可插入多条记录**

sql>insert into 表名 values (值1，值2，…), (值1，值2，…)