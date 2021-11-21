# JavaWeb概述



## 1.XML基础



## 2.HTTP协议



### 1.概念:

**Hyper Text Transfer protocol超文本传输协议**



### 2.传输协议:

**定义了,客户端和服务器端通信时,发送数据的格式**



### 3.特点：

#### 	1.基于TCP/IP的高级协议

#### 	2.默认端口号:80

#### 	3.基于请求/响应模型的:一次请求对应一次响应

#### 	4.无状态的:每次请求之间相互独立,不能交互数据



### 4.历史版本

* **1.0：每一次请求响应都会建立新的连接**
* **1.1：复用连接**



* **响应字符串格式**

	* ```html
		HTTP/2.0  200 OK
		Content-Type: text/html; charset=utf-8
		Content-length: 101
		Date: Wed. 06 Jun 2018 07: 08: 42 GMT
		<html>
			<head>
				<title>$Title$</title>
			</head>
			<body>
			hello, response
			</body>
		</html>
		```

		



## 3.Tomcat


### tomcat下载地址https://tomcat.apache.org/


### IDEA 与 tomcat 相关配置



### 1.IDEA会为每一个tomcat部署的项目单独建立一份配置文件

* **查看控制台的log：Using CATALINA_BASE:   "C:\Users\Fluoxetine\.IntelliJIdea2018.2\system\tomcat\Tomcat_9_0_35_myTomcat_2"**



### 2.工作空间项目和 tomcat部署的web项目



* **tomcat真正访回的是" tomcat部署的web项目”," tomcat部署的web项目”对应着”工作空间项目”的web目录下的所有资源**

* **WEB-INF目录下的资源不能被浏览器直接访问。**



### 3.断点调试:使用debug启动
