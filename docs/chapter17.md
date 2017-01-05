<h1>第17章 网站发布</h1>

# 网站发布方法

1.网站发布概念

- **网站发布就是将开发完成的网站安装到Web服务器上，正式在Internet上提供Web信息服务的实现过程。**
- **网站发布包括两方面的发布：网页的发布和数据库内容的发布。**

2.网站的发布方法

- **网站发布包括两方面的发布：网页的发布和数据库内容的发布。**
- **网页的发布方法主要有三种：手工发布、Web发布、FTP发布。**
- **数据库的发布只有手工的方式进行发布。**

# 数据库的发布

3.数据库发布方法一：手工方式

**①导出开发的数据库：**

**%MySQL%\bin〉mysqldump –u 用户名 –p口令 数据库名称 > 导出SQL文件名.sql**

**%MySQL%\bin〉mysqldump –u root –pmypassword library > c:\mysql\backup\library20070915.sql**

**②发布数据库：将Web数据库的.sql文件导入到Web数据库发布服务器中**

**导入数据库的命令格式如下：**

**%MySQL%\bin〉mysql –u 用户名 –p口令 < 导入SQL文件名.sql**

**例如，%MySQL%\bin〉mysql –u root –pmypassword < c:\mysql\backup\library20070915.sql**

4.数据库发布方法二：MySQL-Front工具

![](https://ww2.sinaimg.cn/large/006tNc79jw1fbg8vcsq2jj30cr0b3mz3.jpg)

# 网页的发布

5.网页发布方法一：手工方式

- **U盘**
- **活动硬盘**
- **光盘**
- **Email**

6.网页发布方法二：Web方式

![](https://ww2.sinaimg.cn/large/006tNc79jw1fbg8vwh239j30ig08g3zw.jpg)

7.网页发布方法三：FTP方式

![](https://ww1.sinaimg.cn/large/006tNc79jw1fbg8wmii3sj30dy0ah3ze.jpg)