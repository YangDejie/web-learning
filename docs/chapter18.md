<h1>第**18**章Apache+MySQL+PHP动态网站平台的搭建</h1>

# **18.1 Apache+MySQL+PHP**开发环境介绍 ★



- Apache


- - 当今互联网使用最广泛的Web服务器 


- PHP


- - 用来解析PHP代码的插件 


- MySQL


- - 多线程的，结构化查询语言(SQL)开源数据库系统


- WAMP，是Windows系统下的Apache+Mysql+PHP组合



- PHPMyAdmin


- - 开源
  - 运行在PHP环境中的MYSQL管理软件


- MYSQL-front
- - - 运行于微软平台的GUI的mysql管理器 

- MyODBC


- - 在Windows上的ODBC驱动程序


- 掌握  


- - 安装
  - 配置
  - 启动
  - 测试



# **18.2 **开发环境的安装与配置★

18.2.1 Apache

- bin目录


- - 包括一个名为ad.exe的服务器调试工具


- conf目录


- - httpd.conf文件


- logs目录
- htdocs目录


- - 是默认的web主目录，


- **Apache**的配置  httpd.conf文件


- - ①DocumentRoot "C:/Program Files/Apache Group/Apache2/htdocs"

   这个是设置网站根文件夹的参数，网站所有的文件将应该放置在该目录下，一定要确保这个文件夹已经事先创建，这个文件夹也就是站点目录。

    为安全起见，站点目录一般要移出系统盘，例如，本书示例更改为"D:/www"。

- - ②`<Directory "C:/Program Files/Apache Group/Apache2/htdocs">`

    同上，跟着上一步一起修改为：`<Directory "D:/www">。`

- - ③DirectoryIndex index.html index.html.var

    这个是服务器默认打开的主页文档类型，可以添加多个文件名，它们将按照排列的先后顺序依次选择主页文件。

   现在修改为 "DirectoryIndex index.html index.php index.htm"，中间用空格隔开。该项修改可以使index.php是主页文件。

- - ④AddDefaultCharset ISO-8859-1

   默认显示的语言，更改为"AddDefaultCharset gb2312"。

- - ⑤Options Indexes FollowSymLinks

   如果想要禁止主页浏览，去掉其中的indexes即可，即改成：Options FollowSymLinks

- - ⑥ServerRoot "C:/Program Files/Apache Group/Apache2"

    安装的Apache服务器的根路径，不用更改。

- - ⑦Timeout 300

    超时设置。如果客户端300秒还没有连接服务器，或者服务器300秒还没有将数据发送到客户端，就会自动断线。。 

- **⑧MaxKeepAliveRequests 100**

**设置支持最大在线请求数目，根据**Web**服务器需要能同时支持的请求数目和**Web**服务器配置来确定。

- **⑨Listen 80**

   Apache2**监听端口，一般情况下不用改，这就是网站的**http**缺省端口号。

- **⑩PidFile logs/httpd.pid**

   Apache.exe**进程的**PID**存放在**httpd.pid**文件中。

- **Apache**的启动和关闭 


- - 方法一：通常是使用Apache自带的Apache Service Monitor工具。 
  - 方法二：是通过操作系统的控制面板进行。


- - - 管理工具—服务 


- - 方法三：通过命令行方式进行。 


- - - 启动：apache -k restart 
    - 关闭：apache -k shutdown 

18.2.2 PHP

- **PHP5**的安装 


- - ①解压php压缩包php-5.4.7-Win32-VC9-x86
  - ②复制PHP目录下的PHP5ts.dll到C:\WINDOWS\system32目录下
  - ③复制PHP.ini-dist或PHP.ini-recommended文件复制到c:\Windows\目录下,并且重命名为PHP.ini； 


- - ④PHP在Apache服务器中的挂载：


- - - 文件httpd.conf中


- - - - LoadModule php5_module "C:/PHP/php5Apache2.dll"
      - AddType application/x-httpd-php .php

  - ⑤重启Apache使修改生效。
  - ⑥用记事本创建一个PHP文件，内容只有一行：<?php phpinfo();?>，将其保存为info.php，放在更改后的web根目录“D:/www”里
  - 然后在浏览器地址栏中输入：http://127.0.0.1/info.php，

php.ini

- ​
- engine=On：设置脚本语言引擎在Apache下有效
- zend.ze1_compatibility_mode = Off：设置与PHP4.*引擎是否兼容
- short_open_tag = On：是否允许<?...?>短标志符，标准标志符：<?PHP … ?> 或 <script language=“PHP”> … </script>
- asp_tags=Off：是否允许ASP风格标记<% … %>
- safe_mode = Off：运行在安全模式
- safe_mode_exec_dir =  ：安全模式只能在该目录中执行文件
- max_execution_time = 30：脚本执行最大秒数
- max_input_time = 60：脚本输入数据分析的最大秒数
- memory_limit = 8M：脚本使用最大内存数
- display_errors = On：是否显示错误
- include_path=“.;C:\Program Files\PHP Home Edition 2\Apache2\php\“：设置include目录
- doc_root = ：设置PHP文件的根目录
- user_dir = ：用户脚本文件目录
- mysql.allow_persistent = On：MySQL数据库支持
- sybase.allow_persistent = On：sybase数据库支持
- mssql.allow_persistent = On：SQlServer数据库支持

18.2.3 MySQL

- 启动


- - 方式一  控制面板
  - 方式二


- - - **net start mysql**
    - **net stop mysql** 

- 配置**MySQL**
- my.ini文件是MySQL的配置文件 
- 修改php.ini文件；
- 找到;extension=php_mysql.dll，去掉前面注释用的";"；
- 然后将以下三个动态连接库文件C:\PHP\libmysql.dll、C:\PHP\ext\php_mysql.dll、C:\PHP\ext\php_mysqli.dll拷贝到C:\Windows\system32下；
- 重启Apache，PHP5就支持mysql了。 



# **18.3 **相关软件工具 ★

- WampServer


- - 是windows下Apache Web服务器、PHP解释器以及MySQL数据库的一个整合软件包。
  - 该软件会自动完成PHP扩展、Apache模块、MySQL数据库的配置整合，不用再手动去修改各项配置文件。
  - 通过WampServer的管理界面就可以开启和关闭各项服务，非常方便
  - 这个软件是免费的。