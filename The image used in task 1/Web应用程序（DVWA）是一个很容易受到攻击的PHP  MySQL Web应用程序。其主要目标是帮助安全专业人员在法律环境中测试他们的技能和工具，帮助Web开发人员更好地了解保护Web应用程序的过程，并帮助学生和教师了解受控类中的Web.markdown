
# 一、安装应用 #
### 1、下载并安装win7x64SP1版本 ###
这里附上下载链接 

百度云盘链接[https://pan.baidu.com/s/1dDvQW3R](https://pan.baidu.com/s/1dDvQW3R)、

至于安装就不再多述
这里分享图文教程 包括虚拟机安装教程

[https://mp.weixin.qq.com/s?src=11&timestamp=1579325878&ver=2103&signature=Blh-GdPxpJLwLJaaBMTA6PK4wSP3ERnWjgYVQ*N31CWOXUXfNMWxdYnBNREVvp3YkYh6KEJD4ZJ6s69aAALsw8viceOzRcZpzvh8PKAZtIeaWGBHW7i7Gmlmq2izuYQ2&new=1](https://mp.weixin.qq.com/s?src=11&timestamp=1579325878&ver=2103&signature=Blh-GdPxpJLwLJaaBMTA6PK4wSP3ERnWjgYVQ*N31CWOXUXfNMWxdYnBNREVvp3YkYh6KEJD4ZJ6s69aAALsw8viceOzRcZpzvh8PKAZtIeaWGBHW7i7Gmlmq2izuYQ2&new=1)
或

[https://blog.csdn.net/weixin_43465312/article/details/92662519](https://blog.csdn.net/weixin_43465312/article/details/92662519)

最后安装完成

<img src="C:\Users\master\Desktop\1.png" style="zoom:75%;" />


# 二、安装配置ZVulDrill网站  #
在GitHub里下载ZVulDrill文件包[https://github.com/710leo/ZVulDrill](https://github.com/710leo/ZVulDrill "github ZVulDrill库") 

安装phpStudy [https://www.xp.cn/](https://www.xp.cn/ "phpstudy官网") 调试环境程序集成包
![Image text](2.png)

分别打开 Apache 和 MySQL

![Image text](4.png)

通过软件网站选项打开网页 查看效果 

![Image text](5.png)

并且 同时打开网页根目录将我们的ZVulDrill web漏洞演示平台文件拷入

![Image text](6.png)

**修改phpstudy_pro\WWW\ZVulDrill\sys\config.php 文件
添加password 密码**

![Image text](7.png)

在数据库里 选择创建数据库(**这里需要提前修改root密码**)分别填入相应的数据库名称和用户名密码（*这里的用户名不能使用root ，我已修改为admin*）

![Image text](10.png)

导入数据库，在新建数据库操作后 选择导入 浏览地址\phpstudy_pro\WWW\ZVulDrill\sys\zvuldrill.sql

![Image text](11.png)

最后再次打开网站 并添加合适的后缀

![Image text](12.png)

# 三、安装配置DVWA网站  #
###  **1**、认识DVWA  ###

### Web应用程序（DVWA [http://www.dvwa.co.uk/](http://www.dvwa.co.uk/ "官网")）是一个很容易受到攻击的PHP / MySQL Web应用程序。其主要目标是帮助安全专业人员在法律环境中测试他们的技能和工具，帮助Web开发人员更好地了解保护Web应用程序的过程，并帮助学生和教师了解受控类中的Web应用程序安全性房间环境。

DVWA的目标是通过简单直接的界面练习一些最常见的Web漏洞，具有各种难度。请注意，此软件存在记录和未记录的漏洞。

DVWA共有十个模块，分别是:
Brute Force（暴力（破解）
Command Injection（命令行注入）
CSRF（跨站请求伪造）
File Inclusion（文件包含）
File Upload（文件上传）
Insecure CAPTCHA （不安全的验证码）
SQL Injection（SQL注入）
SQL Injection（Blind）（SQL盲注）
XSS（Reflected）（反射型跨站脚本）
XSS（Stored）（存储型跨站脚本）
同时每个模块的代码都有4种安全等级：
###  Low(低级)、Medium(中级)、High(高级)、Impossible(不可能级别)  ###
通过从低难度到高难度的测试并参考代码变化可帮助学习者更快的理解漏洞的原理。

<!--原文链接：https://blog.csdn.net/qq_38778137/article/details/83792188-->

2、下载 DVWA漏洞平台文件[https://github.com/ethicalhack3r/DVWA](https://github.com/ethicalhack3r/DVWA)
拷入文件到根目录下
![Image text](14.png)
修改 E:\phpstudy_pro\WWW\DVWA\config\config.inc.php 文件 （php文件将.dist删了就可以了）
修改数据库名称、用户名和密码
![Image text](15.png)
在软件里添加数据库
![Image text](16.png)


打开网站 [http://localhost:80/dvwa/setup.php](http://localhost:80/dvwa/setup.php)
![Image text](17.png)
点击**Create / Reset Database **
![Image text](18.png)

进入登陆界面 默认用户 admin 密码 password
![Image text](19.png)
![Image text](20.png)


# 四、开启telnet服务  #
在 控制面板 --> 程序 --> 程序与功能 右边的打开或关闭Windows功能出 找到 telnet服务 并勾上 点击 确定
![Image text](21.png)
当然，也可以通过telnet命令查看 远程登陆命令是否开启

![Image text](22.png)
![Image text](23.png)
# 五、FTP服务器 # 
设置ftp服务方法很多 这里介绍3个
### 1、 ###

首先设置虚拟机网络适配器 为NAT模式（*方便以后和其他虚拟机通信*）
![Image text](24.png)
并手动设置虚拟机ip 
![Image text](25.png)
这次采用 phpStudy 内自带的ftp服务器
创建一个FTP服务 设置用户名 密码 已经根目录
![Image text](26.png)
开启 FTP服务器 
![Image text](27.png)
在物理界 测试登陆并上传测试文件 在ftp根目录下查看是否有文件上传
![Image text](28.png)


### 2、 ###

采用 FTPServer 软件 （*和上面一步一样需要手动设置IP地址*）

![Image text](30.png)

若 不勾选  验证身份和 填写用户和密码 开启ftp服务器

![Image text](31.png)

则 任意用户都可登陆操作

![Image text](32.png)

勾选验证身份 和填写了用户和密码
其他没授权用户将无法登陆
![Image text](33.png)

### 3、###
windows 自带的FTP服务
先建两个文件夹 分别表示上传文件和下载文件夹
![Image text](34.png)

然后在 我的电脑右键->管理->本地用户和组－>用户->“右键”新建用户－>输入用户名和密码
![Image text](35.png)
点击创建就可以完成
![Image text](36.png)
在 控制面板 --> 程序 --> 程序与功能 右边的打开或关闭Windows功能出 找到 internet服务 在服务下找到 ftp服务 并勾上 点击 确定
![Image text](37.png)
![Image text](38.png)

因为ftp是internet服务的一部分 所以需要将internet服务一起 才能安装成功

![Image text](39.png)


安装完成后 我的电脑右键->管理->服务和应用程序 找到网站 右键添加FTP站点
![Image text](40.png)
根据自己需要设置ftp服务信息

![Image text](41.png)
![Image text](42.png)
![Image text](43.png)

这些设置完成后 在虚拟机本机的浏览器上或者文件夹地址栏里 可以登陆ftp服务器了
![Image text](44.png)

因为防火墙的缘故 我们需要在高级设置里
![Image text](45.png)
找到入站规则 并新建规则
![Image text](46.png)
![Image text](47.png)
![Image text](48.png)
![Image text](49.png)
![Image text](50.png)
同理出站规则也一样新建规则

两个规则都建立完成
![Image text](52.png)
![Image text](53.png)
在物理机上就可以通过身份验证  上传或者下载文件
![Image text](51.png)

# 搭建sqllib #
拷贝我们的sqllib文件到www文件夹目录下
![Image text](60.png)
修改/sql-connections/db-creds.inc 中关于数据库的文件
![Image text](61.png)

在 phpStudy创建 数据库 
![Image text](63.png)

就可以打开 网页[http://localhost/sqli/index.html](http://localhost/sqli/index.html)
![Image text](64.png)
点击Setup/reset Database for labs 却回出现问题
![Image text](65.png)
根据这个解决方法
[https://blog.51cto.com/11834557/2309881](https://blog.51cto.com/11834557/2309881)
但是还是不是太行
![Image text](70.png)


最后，，我选择降php等级 而最有效的办法就算 安装phpStudy2016  各大网页上都可以下载到，这里不提供链接

将sqli-labs 文件包拷入phpStudy_v2016\WWW内 
![Image text](71.png)
修改db-creds.inc文件
![Image text](72.png) 就将pass=“root”就完了。在打开网页

![Image text](73.png) 
![Image text](74.png) 
![Image text](75.png) 
直接就可以用了，根本就不用老费什么麻烦去改代码