<h1>第**9**章 软件平台规划</h1>

- ★★
- 操作系统
- Web服务器
- 应用服务器
- 动态语言
- 数据库
- LAMP(L:Linux、A:Apache、M:MySQL、P:PHP)
- WAMP

# 1 Web服务器操作系统选型

- 操作系统：由硬件决定，决定可以运行的软件以及服务器的安全性和可靠性。
- 应用程序：由操作系统决定。
- Unix Server
- Linux Server
- Windows 2003/2000 Server 

关于Unix

- 1969年，Ken Thompson，AT&T贝尔实验室，DEC PDP-7计算机。
- AT&T对大学或科研机构提供源代码
- BSD UNIX：最早实现TCP/IP。
- UNIX代表：AIX,HP UX,Novell UNIXWare, SCOUNIX, Solaris等
- 主流版本


- - IBM的AIX，
  - Hewlett - Packard的HP - UX，
  - Apple的A/UX，
  - DEC的ULTRIX和DEC OSF/1，
  - Silicon Graphics的IRIX，
  - Sun微系统公司的Solaris，
  - SCO的BSDI和SCO UNIX是一些。

UNIX特点: 关键性业务首选

- 技术成熟、可靠性高：24*365。
- 极强的伸缩性：笔记本、PC、工作站、小型机、巨型机等；支持SMP、MPP和Cluster
- 网络更能强：内核支持。
- 强大数据库支持能力：Oracle,Informix,Sybase等
- 开发功能强：工作站
- 用户界面多样化：命令行输入、X-Window



Linux

- 1991/8/25，Linus Benedict Torvalds，芬兰赫尔辛基大学计算机系学生。
- 主要运行在Intel X86的PC机上。
- 免费，并提供源代码，可以任意修改。
- 强大的网络功能
- 支持多种硬件平台：x86,SPARC,Alpha等。SMP、IA64等
- 可靠稳定：可以运行在关键任务上。

Windows Server

- Microsoft
- 不免费、也不公开源代码
- 各版本间兼容性非常好
- 强大数据库支持能力
- 非常友好的GUI图形用户界面，特别适于初学者
- 非多用户操作系统
- 稳定性、安全性较差



操作系统之间的比较饿选择

- 安全性
- 可靠性
- 易维护
- 易管理
- 熟悉度
- 开发环境
- 价格因素



# 2.Web服务器选型

- HTTP服务器通常也叫做Web服务器
- 它提供在Internet或Intranet上的HTML文档服务，即提供客户使用浏览器访问网站信息的网页，Web服务器不能直接访问数据库，因此Web服务器仅能提供静态页面。

![](https://ww1.sinaimg.cn/large/006y8lVajw1fbg0qq53dxj30e506oglz.jpg)

- 现在最流行的Web服务器有


- - Apache
  - IIS
  - Nginx
  - google
  - Sun Java System Web Server

[http://news.netcraft.com/archives/web_server_survey.html](http://news.netcraft.com/archives/web_server_survey.html) 





1)  Apache

- 一个免费的、稳定的、商业级的和公开程序源代码的HTTP Web 服务器。


- - http://www.apache.org


- Apache是世界使用排名第一的Web服务器软件。它可以运行在几乎所有广泛使用的计算机平台上
- Apache取自"a patchy server"的读音，意思是充满补丁的服务器，因为它是自由软件
- Apache的特点是简单、速度快、性能稳定，并可做代理服务器来使用。

2) IIS

http://www.microsoft.com

- IIS(Internet Information Services)是Microsoft公司的Web服务组件
- 包括Web服务器、FTP服务器、NNTP服务器和SMTP服务器
- IIS仅能用于Windows平台， 
- IIS比Apache更易于配置、管理和维护 
- China accounts for over 30% of all web-facing computers that run Windows Server 2003, making it the largest user of this obsolete operating system 
- IIS的安全脆弱性曾长时间被业内诟病，一旦IIS出现远程执行漏洞威胁将会非常严重
- IIS8的新功能旨在将大规模Web服务器聚集起来。但是在众多功能中一个很好的效果在于怎样分拨更小的服务器甚至单独的服务器。
-  *IIS* *10*.0 Express 是一个针对开发人员进行了优化的简单独立的 *IIS* *10*.0 版本



- 提供ISAPI(Intranet Server API) ISAPI（Internet Server Application Programming Interface）筛选器


- - 作为扩展Web服务器功能的编程接口
  - 整合PHP, JSP,CGI( VC++)


- 提供一个Internet数据库连接器，可以实现对数据库的查询和更新。
- Windows Server 2012 中（IIS 8.0）Web平台提供了在内部和云端托管Web 应用程序的基础，并提供了可扩展的弹性平台，可完整支持开放式业界标准。

3）nignx

- ** (“engine x”)  **俄罗斯
- 供俄国大型的入口网站及搜索引擎Rambler使用
- 高性能的[HTTP](http://baike.baidu.com/view/9472.htm)和[反向代理](http://baike.baidu.com/view/1165595.htm)服务器，IMAP/POP3/SMTP[服务器](http://baike.baidu.com/view/899.htm)


- - 可以支持作为 HTTP[代理服务器](http://baike.baidu.com/view/751.htm)对外进行服务。


- 其将[源代码](http://baike.baidu.com/view/60376.htm)以类BSD许可证的形式发布
- 因它的稳定性、丰富的功能集、示例配置文件和低系统资源的消耗而[闻名](http://baike.baidu.com/view/835047.htm)。
- 2011年6月1日，nginx 1.0.4发布。


- 轻量级的 http server
- **Nginx **可以在大多数 **Unix like OS **上编译运行，并有 **Windows **移植版 
- 其特点


- - 占有内存少，
  - [并发](http://baike.baidu.com/view/684757.htm)能力强，事实上nginx的并发能力确实在同类型的网页服务器中表现较好


- - - 在高连接并发的情况下，Nginx是[Apache](http://baike.baidu.com/subview/28283/5418752.htm)服务器不错的替代品
    - Nginx在美国是做虚拟主机生意的老板们经常选择的软件平台之一。能够支持高达 50,000 个并发连接数的响应
    - 中国大陆使用nginx网站用户有：百度、[京东](http://baike.baidu.com/view/1412737.htm)、[新浪](http://baike.baidu.com/view/2410.htm)、[网易](http://baike.baidu.com/view/6043.htm)、[腾讯](http://baike.baidu.com/view/1591.htm)、[淘宝](http://baike.baidu.com/view/3629.htm)等。



- Nginx作为[负载均衡服务器](http://baike.baidu.com/view/253171.htm)
- Nginx 在内部直接支持 Rails 和 PHP 程序
- Nginx采用C进行编写 
- Nginx是一个安装非常简单、配置非常简洁、Bugs非常少、Nginx启动特别容易，并且几乎可以做到7*24不间断运行，即使运行数个月也不需要重新启动，还能够不间断服务的情况下进行软件版本的升级。

4）gws

- Google Web Server
- 谷歌Web服务器软件，它是基于Apache HTTP服务器基础开发的对谷歌应用程序优化版。
- GWS 是 Google 专用的 Web 服务器
- 是 Google 的服务器列表，顺序依次是“Domain、OS、Web server”。

5）其他

lighttpd：http://[www.lighttpd.net](http://www.lighttpd.net/)

- 开源软件
- Lighttpd具有非常低的内存开销，cpu占用率低，效能好，以及丰富的模块等特点。
- 利用apache的rewrite技术，将繁重的cgi/fastcgi任务交给Lighttpd来完成，充分利用两者的优点。
- Lighttpd现在的版本为Lighttpd 1.4.15。

IBM Lotus Domino Web Server：http://www.ibm.com

- 以跨平台架构为基础，提供跨企业的讯息交流、协同作业、电子商务等Web化应用。
- 群组协同作业达到最佳化。并提供跨平台的群集备援技术、系统故障转移、动态负载平衡、帐户服务等等。让企业电子商务可24小时全天候服务，是企业处理关键应用系统最优质的平 

# 3 应用服务器(中间件)选型★

- 应用服务器中间件又称为“应用服务器软件平台” 
- Web服务器主要完成显示逻辑，将静态页面的信息现在客户端的屏幕上；
- 应用服务器完成业务逻辑，将业务处理的信息数据传递给Web服务器，替换掉嵌入在HTML中的动态语言部分，再由Web服务器传递到客户端显示在屏幕上；
- 数据库服务器完成数据逻辑，提供数据库的管理与维护。 


- 应用服务器(或存取数据库为Web服务器提供数据的服务器平台)现在主要有


- - Tomcat
  - IIS
  - PHP
  - WebSphere
  - WebLogic
  - JBosss
  - [Sun Java System Application Server](http://www.sun.com/software/products/appsrvr/index.xml)
  - Oracle Application Server



- ①Tomcat：http://tomcat.apache.org

  - 免费的开放源代码的Web应用服务器，
  - 它是Apache软件基金会(Apache Software Foundation)的Jakarta项目中的一个核心项目
  - Tomcat现在已是最优秀和最受欢迎的基于java的应用服务器之一。
  - Tomcat和IIS、Apache等Web服务器一样，具有处理HTML页面的功能，
  - 占用的[系统资源](http://baike.baidu.com/view/53557.htm)小，扩展性好，支持负载平衡与邮件服务等开发应用系统常用的功能
  - 目前Tomcat最新版本为**7.0.30**。 
  - ​
  - Tomcat 部分是Apache 服务器的扩展，但它是独立运行的，所以当你运行tomcat 时，它实际上作为一个与Apache 独立的进程单独运行的。 
  - Tomcat不仅能处理动态HTML，还能处理静态HTML，但是处理静态HTML的效力不如Apache HTTP服务器，因此在Tomcat之前一般安装Apache HTTP服务器。


  - - 这里的诀窍是，当配置正确时，Apache 为HTML页面服务，而Tomcat 实际上运行JSP 页面和Servlet。


  - Tomcat 是一个轻量级应用[服务器](http://baike.baidu.com/view/899.htm)，在中小型系统和并发访问用户不是很多的场合下被普遍使用，是开发和调试JSP 程序的首选。


  - - Tomcat+MyEclipse


  - 它还是一个Servlet和JSP[容器](http://baike.baidu.com/view/864334.htm)，独立的Servlet容器是Tomcat的默认模式。

- ②IIS：[http://www.microsoft.com](http://www.microsoft.com/)

  - IIS不仅能解释HTML页面，还能解释ASP的动态页面-访问数据库。
  - IIS是目前最流行的Web(应用)服务器产品之一
  - ASP、ASP.NET、CGI 脚本、Microsoft 的 FrontPage® 2002 Server Extensions 以及 WebDAV 发布功能。 

- ③PHP：http://www.php.net

  - PHP超文本预处理器(Hypertext Preprocessor)作为Web开发的免费、提供源代码的脚本语言
  - 它用于管理动态内容、支持数据库、处理会话跟踪，甚至构建整个电子商务站点，它可以直接连接数据库


  - - 如Mysql，Oracle，Sybase，Informix，Microsoft SQLServer，Access 等，
    - 还完全支持ODBC接口，用户更换平台时，无需变换PHP代码。 

- ④IBM WebSphere：http://www.ibm.com

  - WebSphere 是 IBM 的集成软件平台。
  - [WebSphere Application Server](http://www.ibm.com/developerworks/websphere/zones/was/newto/) 是该基础设施的基础，其他所有产品都在它之上运行 
  - WAS是一种功能完善、开放的Web应用程序服务器，是IBM电子商务计划的核心部分，它是基于J2EE 1.4的应用环境，用于建立、部署和管理Internet和 Intranet Web应用程序或应用客户端程序 
  - WAS现在已是中大型电子商务或企业应用开发、管理和部署的热选平台之一，与WebLogic齐名 

- ⑤BEA WebLogic：http://www.bea.com.cn

  - BEA WebLogic Server 是一种多功能、基于J2EE 1.4标准的web应用服务器，
  - 为企业构建自己的应用提供了坚实的基础。
  - 各种应用开发、部署所有关键性的任务，无论是集成各种系统和数据库，还是提交服务、跨 Internet 协作，起始点都是 BEA WebLogic Server 

- ⑥[JBoss](http://www.itisedu.com/phrase/200605111343075.html) Application Server：http://www.jboss.com

  - [JBoss](http://www.itisedu.com/phrase/200605111343075.html)是一个[开源](http://www.itisedu.com/phrase/200603091812115.html)的符合[J2EE](http://www.itisedu.com/phrase/200603091447335.html)规范的应用服务器，
  - 作为J2EE规范的补充，Jboss中引入了[AOP](http://www.itisedu.com/phrase/200604231341385.html)[框架](http://www.itisedu.com/phrase/200603061723295.html)，为普通Java[类](http://www.itisedu.com/phrase/200603090857555.html)提供了J2EE服务
  - JBoss是一个运行EJB的J2EE应用服务器，例如：[数据库](http://www.itisedu.com/phrase/200602271218062.html)访问[JDBC](http://www.itisedu.com/phrase/200604151904545.html)、交易(JTA/JTS)、[消息](http://www.itisedu.com/phrase/200603090938465.html)机制(JTS)、命名机制(JNDI)和管理支持([JMX](http://www.itisedu.com/phrase/200604261751455.html))。 
  - JBoss应用服务器已经真正发展成具有企业强度(即支持关键性任务的应用)的应用服务器。。

- ⑦[Sun Java System Application Server](http://www.sun.com/software/products/appsrvr/index.xml)：http://cn.sun.com

  - [Sun Java System Application Server](http://www.sun.com/software/products/appsrvr/index.xml)是一个与Java 2平台企业版（J2EE平台）兼容的应用程序服务器，用来开发和发送服务器端的应用程序和Web服务。

  ⑧Oracle Application Server：[http://www.oracle.com](http://www.oracle.com/)

  - Oracle应用服务器是[Oracle 融合中间件](http://www.oracle.com/lang/cn/products/middleware/index.html)的一个关键组件 



# 4 Web数据库服务器⭐️

- Web数据库主要是指关系数据库，


- - Oracle
  - Sybase
  - DB2
  - SQLServer
  - MySQL
  - Access


- Oracle是世界领先的信息管理软件供应商和世界第二大独立软件公司。
- Sybase是全球公认的在数据密集应用领域有杰出的性能表现的领导者。全球的金融服务、通信、制造和政府等的业务关键系统提供强劲动力。
- DB2是IBM公司的一个重要软件产品
- 微软数据库的最新代表产品是SQL Server 2012。



- MySQL是中小企业网站Linux平台的首选自由数据库系统，也是中小型网站首选Web数据库


- - 数据库，一般像起点中文网，晋江这样的小说网站都用什么数据库？


- Access是由[微软](http://zh.wikipedia.org/w/index.php?title=%E5%BE%AE%E8%BB%9F&variant=zh-cn)发布的[桌面数据库管理系统](http://zh.wikipedia.org/w/index.php?title=%E9%97%9C%E8%81%AF%E5%BC%8F%E8%B3%87%E6%96%99%E5%BA%AB%E7%AE%A1%E7%90%86%E7%B3%BB%E7%B5%B1&variant=zh-cn)
- 阿里自主研发数据库**OceanBase**


- - [腾讯云**-**云数据库**100%**兼容**MySQL**，安全稳定**!**](http://www.baidu.com/baidu.php?url=0000000wxBrCAbpPeUGLeP4F56-ar02WwCiiSICJ_OhMmtbD6rQueS7KyRBLTZzra5uzVM_2BgB22hAwPLSn7HDcStbx9VzjHsUIZvhyvnITjIlYkT9Lyv1-hm23giC9vC1W0LY.7b_jvfYgmQbfysfLgtSSa9G4mLmFCR_m3mYlpS8a9G4I2UM3PQ7qvoQbtILgKfYt_QrMAzORN2s1f_NqMuElN0.U1Yz0ZDq_2Q0eejP_nY-nWj2OUeIESc0IjLRk_oqEVvO36KGUHYznjf0u1dBugK1nfKdpHdBmy-bIfKspyfqnWR0mv-b5HD4P6KVIjYknjDLg1nsnH7xnH0krfKopHYs0ZFY5HDdP0K-pyfqnHfzrNtkrH01Pdtkrjc3nNtznHDkrNtznH0YndtznHD4nNtznHnYn0KBpHYznjwxnHRd0AdW5HckP1nvPjfLrNtkg1ckP1nLnW0vnfKkTA-b5H00TyPGujYs0ZFMIA7M5H00ULu_5HcdP1fVuZGxnWmvridbX-tzPWm4yadbX-tzP1TYQywlg1nYrHmVn-tYnjnvQywlg1fdrjnVn-tYP1bkQywlg1f3n1cVnNtYrHbkQywlg1RsPWbVuZGxPHD1PadbX-tdnHbsQHFxPHcYraYkg1RzrjRVuZGxPHnzraYkn7tdn1mzQH7xPHfsPBdbX-tdP1cVuZC0mycqn7ts0ANzu1Ys0ZKs5H00UMus5H08nj0snj0snj00Ugws5H00uAwETjYs0ZFJ5H00uANv5gKW0AuY5H00TA6qn0KET1Ys0AFL5H00UMfqn0K1XWY0IZN15HR4rHR1njDkPHf1nWfdnWmdPWR0ThNkIjYkPjTvPWTsPWTzPjTz0ZPGujd-rARvrjT4nj0snjK-P1wh0AP1UHdKwWbsPjuArjn4PH-7nYRk0A7W5HD0TA3qn0KkUgfqn0KkUgnqn0KlIjY1)





# 9.5 动态网页设计语言选型 ★

- 现在服务器端技术主要有CGI、PHP、ASP、JSP
- CGI不是一种动态网页设计语言
- PHP、ASP和JSP是当今最常用的三种动态网页设计语言
- ruby on rails

CGI

- 不是一种语言，它是用于HTML窗体和应用程序之间通信的简单协议(接口)。
- 许多语言可以用来编写CGI，包括Perl，C或者Shell脚本。
- CGI文件一般使用.cgi或者.pl作为文件扩展名，通常位于cgi-bin或者scripts目录下。


- CGI主要的缺点是


- - ①客户端与后端数据库服务器通信必须通过Web服务器，且Web服务器要进行数据与HTML文档的互相转换，当多个用户同时发出请求时，必然在Web服务器形成信息和发布瓶颈。
  - ②CGI应用程序每次运行都需打开和关闭数据库连接，效率低，操作费时；
  - ③CGI应用程序不能由多个客户机请求共享，即使新请求到来时CGI程序正在运行，也会启动另一个CGI应用程序-进程，


- - ④由于SQL与HTML差异很大，CGI程序中的转换代码编写繁琐，维护困难；
  - ⑤安全性差，缺少用户访问控制，对数据库难以设置安全访问权限；
  - ⑥HTTP协议是无状态且没有常连接的协议，DBMS事务的提交与否无法得到验证，不能构造Web上的OLTP应用。s





三种动态语言

- ASP：Active Server Pages，Microsoft，使用VBScript或JavaScript脚本语言。
- PHP：跨平台，完全免费，提供源码，Http://www.php.net
- JSP：Sun公司开发的跨平台语言，JDK，J2EE，。
- ​
- 这三种动态网页语言都是嵌入在HTML中
- HTML主要描述信息的显示样式；动态语言处理服务器端的逻辑，需要附加的语言引擎分析和执行程序代码。



PHP hypertext preprocessor

- 平台无关性，  开源
- PHP动态网页设计语言其语法利用了C，Java 和 Perl，非常容易学习，
- 面向对象编程，PHP+MySQL，支持个数据库的接口
- PHP可跨操作系统平台和Web服务器平台
- PHP缺乏规模支持，缺乏多层结构支持。另外PHP提供的专用数据库接口支持也不统一，这就使得它不适合运用在电子商务中，PHP特别适于中小型网站或大型网站的某些频道或专栏。



ASP Active Server Pages

- Microsoft公司产品，只能运行在微软平台。
- 简洁的设计和实施，语言灵活，并支持复杂的面向对象特性，特别适于初学者的学习与编程
- 安全性，平台局限
- 在内存使用和执行时间方面耗费非常大，这大部分归因于较长的代码路径。内存使用率还可能成为Web服务器上的一个问题。
- ASP.NET比较适于安全程度要求不是太高、运行效率要求也不是很苛刻的情况，不适于电子商务网站。



JSP java Server Pages

- 几乎运行于所有操作系统平台，
- 运行速度快、安全性也高，因此JSP一般用于电子商务网站或中、大型企业网站
- 但开发代码比PHP和ASP复杂，
- JSP的执行方式和ASP或PHP完全不同。


- - 在JSP首次被执行的时候，JSP文件被Java虚拟机编译成Servlet代码，以后就不需要编译了，直到该段JSP代码变更了再重新进行编译成Servelet，由生成的Servlet来对客户端应答，
  - ASP、PHP边解释边执行、无需编译，
  - 因此JSP运行效率要比ASP、PHP要高得多。
  - JSP可以看做是Servlet的脚本语言版
  - PHP4也已经在Zend的支持下，实现编译运行


- JSP的解释引擎(或应用服务器)主要有：


- - Tomcat
  - WebSphere、
  - WebLogic、
  - JBoss、
  - Sun Java System Application Server Platform Edition、
  - Oracle Application Server等

所以亚马逊，ebay，苏宁，淘宝，支付宝 都主要采用Java作为开发平台，京东也在往Java上面转。

Java比较有优势：

- 1 开源提供的解决方案比较多，例如jpa，hadoop，jboss，esb，消息中间件
- 2 Java比较适合大型团队，比如上百上千的开发团队，因为语法死板，有一定的编程规范，每个人写出的代码的风格不会有太大的差异。



**Java**存在的问题也有很多

- 1 Java的框架太多，每个公司用的都不一样，而且版本混乱，有一些很重量级的
- 2 开源产品同类的多，需要取舍，而且有一些自以为很牛逼的架构师喜欢在开源的产品上封装，搞自己的框架，搞的各个公司的框架都不一样，学习成本高。光一个xml解析工具，都有几十种。
- 3 开发效率向相当低，远远比PHP，Python这些静态语言低很多

所以对于web2.0这样的网站来说，非常不适合用Java。我比较赞同使用PHP或者Python （paɪθən) 。比如豆瓣，优酷。





- JSP、ASP、PHP来源不同的技术规范
- JSP、PHP跨平台，ASP主要运行在微软平台
- JSP、PHP免费提供，并开放源代码，受到很多公司的支持；ASP仅依靠微软公司开发推动
- JSP: 一次编写，各处运行。JSP组件可重用性。
- JSP编译运行，ASP、PHP脚本级运行(PHP4已可以在Zend支持下，实现编译运行)；
- PHP是中小型网站的首选。
- 不管哪种语言，技术到家了，都可以开发出漂亮的页面。





ruby  on rails

- Rails是一个 Web 应用程序框架
- 构建在 Ruby 语言之上
- 不同于已有复杂的Web 开发框架，Rails是一个更符合实际需要而且更高效的Web开发框架。
- Rails结合了PHP体系的优点（快速开发）和Java体系的优点（程序规整）