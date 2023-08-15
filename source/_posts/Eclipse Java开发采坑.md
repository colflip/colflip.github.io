---
title: Eclipse Java开发采坑
mathjax: true
tags:
  - Eclipse
  - Java
  - 采坑
categories: 编程开发
date: 2019-02-02 10:54:13
---
<!-- more -->
## eclipse无法解析导入 javax.servlet 的解决方法
出现上述问题的原因是你的Eclipse项目没有导入JSP运行所需要的Tomcat类库，主要是servlet-api.jar文件(或者servlet.jar），tomcat容器里面有这文件，在以下位置：%Tomcat_Home%/common/lib/servlet-aip.jar,要将其导入到项目的构建路径中(如果你用的是Eclipse).

导入方法：右击你的Eclipse项目，选择 “构建路径”--“配置构建路径”。点击“库”选项卡，单击右边的“添加库”按钮，在出现的“添加库”对话框中选中“服务器运行时”，单击“下一步”，在出现的对话框中选中你使用的Tomcat服务器,例如，我的是：Apache Tomcat v5.5,单击“完成”既可。这时你的Tomcat类库就添加到当前项目中了。
依次展开Java Resources: src->Libraries，就能看到Apache Tomcat v5.5[Apache Tomcat v5.5]类库已经添加到当前项目中了。

## request中的setCharacterEncoding方法不识别
request中的setCharacterEncoding方法作用是用指定的编码集去覆盖request对象中的默认的”ISO-8859-1”编码集，这样request.getParameter(“”)方法就会用新的编码集去解码，必须在第一次使用request时就要调用这个方法来设置编码集，否则该方法就会无效。
单独加载weblogic.jar，应为它会用到request上网上说servlet-api.jar版本必须在2.4之后面的方法都试过后，我的setCharacterEncoding（“utf-8”）方法依然不识别；简直气人啊；最后用 where java 命令查看安装的jdk发现jdk地址显示“c:\programData\Oracle\java\javapath……java.exe”和环境变量配置的地址不一样，果断删除，并将path环境变量里的jdk相关配置放到最前面。

## 启动Tomcat服务器报错：
Several ports (8005, 8080, 8009) required by Tomcat v5.5 Server at localhost are already in use. The server may already be running in another process, or a system process may be using the port. To start this server you will need to stop the other process or change the port number(s).

解决方法：

方法1：杀掉占用端口的软件。
打开任务管理器，找到java虚拟机相关的进程javaw.exe，将它结束掉。

方法2：修改tomcat默认端口号。
修改Tomcat的配置文件。
例如：C:/tomcat5.5.25/conf/server.xml
```bash
 <Connector port="8080" maxHttpHeaderSize="8192"
               maxThreads="150" minSpareThreads="25" maxSpareThreads="75"
               enableLookups="false" redirectPort="8443" acceptCount="100"
               connectionTimeout="20000" disableUploadTimeout="true" />
```
Connector 节点，将port="8080"中的端口改为一个没有被占用的端口。
