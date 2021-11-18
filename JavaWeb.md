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





### IDEA 与 tomcat 相关配置



### 1.IDEA会为每一个tomcat部署的项目单独建立一份配置文件

* **查看控制台的log：Using CATALINA_BASE:   "C:\Users\Fluoxetine\.IntelliJIdea2018.2\system\tomcat\Tomcat_9_0_35_myTomcat_2"**



### 2.工作空间项目和 tomcat部署的web项目



* **tomcat真正访回的是" tomcat部署的web项目”," tomcat部署的web项目”对应着”工作空间项目”的web目录下的所有资源**

* **WEB-INF目录下的资源不能被浏览器直接访问。**



### 3.断点调试:使用debug启动



# 3.Servlet基础



## 1.Servlet概述

### ==Servlet： server applet==

### ==概念:运行在服务器端的小程序==

```java
/*
Servlet就是一个接口,定义了]ava类被浏览器访同到( tomcat识别)的规则。
将来我们自定义一个类,实现 Servlet接口,夏写方法。
*/
```

## 2.Servlet快速入门

### 1.创建 JavaEE项目

### 2.定义一个类,实现 Servlet接口

```java
public class Servletdemol implements Servlet
```

### 3.实现接口中的抽象方法

### 4.配置 Servlet

```java
web.xml文件

<!-- 配置Servlet -->
<servlet>
    <servlet-name>Demo1</servlet-name>
    <servlet-class>com.itrs1.web.servlet.servlet</servlet-class>
</servlet>

<servlet-mapping>
    <servlet-name>Demo1</servlet-name>
    <url-pattern>/Demo1</url-pattern>
</servlet-mapping>
```

```java
package com.itrs1.web.servlet;

import javax.servlet.*;
import java.io.IOException;

public class servlet implements Servlet {


    @Override
    public void init(ServletConfig servletConfig) throws ServletException {

    }

    @Override
    public ServletConfig getServletConfig() {
        return null;
    }

    //提供服务的方法
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("hello Servlet");
    }

    @Override
    public String getServletInfo() {
        return null;
    }

    @Override
    public void destroy() {

    }
}
```

==浏览器搜索[localhost:8080/Demo1]==

==刷新几次，idea中Servlet窗口弹出hello Servlet几次==

## 3.Servlet执行原理



##### 1.当服务器接受到客户端浏览器的请求后,会解析请求URL路徑,获取访问的 Servlet的资源路径

##### 2.查找 web. xm文件,是否有对应的==<ur1- pattern>==标签体内容。

##### 3.如果有,则在找到对应的< servlet- class:全类名

##### 4.tomcat会捋字节码文件加载进内存,并且创建其对象

##### 5.调用其方法



## 4.Servlet生命周期

### 1.被创建:执行init方法,只执行一次

* **Servlet什么时候被创建?**

* **默认情况下,第一次被访问时, Servlet被创建**

* **可以配置执行 Servlet的创建时机**

```html
<!-- 配置Servlet -->
<servlet>
	<servlet-name>Demo2</servlet-name>
    <servlet-class>com.itrs1.web.servlet.ServletDemo2</servlet-class>
    <!--
    	指定Servlet的创建时机
        在<servlet>标签下配置
        1.第一次被访问时，创建
            *<load-on-startup>的值为负数
        2.在服务器启动时，创建
            *<load-on-startup>的值为0或正整数
    -->
    <load-on-startup>-5</load-on-startup>
</servlet>

<!--
Servlet的init方法,只执行一次,说明一个Servlet在内存中只存在一个对象, Servlet是单例的
	*多个用户同时访问时,可能存在线程安全问题。
	*解决:尽量不要在 Servlet中定义成员变量。即使定义了成员变量,也不要对修改值
-->
```

### 2.提供服务:执行 service方法,执行多次

* **每次访问 Servlet时, Service方法都会被调用一次。**

### 3.被销毁:执行 destroy方法,只执行一次

* **Servlet被销毁时执行。服务器关闭时, Servlet被销毁**
* **只有服务器正常关闭时,才会执行 destroy方法**
* **destroy方法在 Servlet被销毁之前执行,一般用于释放资源**

```java
package com.itrs1.web.servlet;

import javax.servlet.*;
import java.io.IOException;

/*
    Servlet的方法
 */
public class ServletDemo2 implements Servlet {

    /**
     * 初始化方法
     * 在Servlet被创建的时候，执行。只会执行一次
     * @param servletConfig
     * @throws ServletException
     */
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {
        System.out.println("init.....");
    }

    /**
     * 获取ServletConfig对象
     * ServletConfig：Servlet的配置对象
     * @return
     */
    @Override
    public ServletConfig getServletConfig() {
        return null;
    }

    /**
     * 提供服务方法
     * 每一次Servlet被访问时，执行。执行多次
     * @param servletRequest
     * @param servletResponse
     * @throws ServletException
     * @throws IOException
     */
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("service.....");
    }

    /**
     * 获取Servlet的一些信息，版本，作者等等。。
     * @return
     */
    @Override
    public String getServletInfo() {
        return null;
    }

    /**
     * 销毁方法
     * 在服务器正常关闭时，执行。执行一次
     */
    @Override
    public void destroy() {
        System.out.println("destroy.....");
    }
}
```

## 5.Servlet 3.0 注解配置

https://www.bilibili.com/video/BV1qv4y1o79t?p=237

### 1.好处

* #### 支持注解配。可以不需要web.xml了

### 2.步骤

#### 			1.创建JavaEE项目,选择 Servlet的版本3.0以上,可以不创建web.xml

#### 2.定义一个类,实现 Servlet接口

#### 3.复写方法

#### 4.在类上使用@WebServlet注解,进行配置

* #### @webservlet("资源路径")

	```java
	@WebServlet("/demo2")
	```

```java
package com.itrs.web;

import javax.servlet.*;
import javax.servlet.annotation.WebServlet;
import java.io.IOException;

@WebServlet("/demo2")
public class ServletDemo implements Servlet {
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {

    }

    @Override
    public ServletConfig getServletConfig() {
        return null;
    }

    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        System.out.println("Servlet4.0.....");
    }

    @Override
    public String getServletInfo() {
        return null;
    }

    @Override
    public void destroy() {

    }
}
```

* ###### ==WebServlet源码==

```java
  // IntelliJ API Decompiler stub source generated from a class file
  // Implementation of methods is not available

package javax.servlet.annotation;

@java.lang.annotation.Target({java.lang.annotation.ElementType.TYPE})
@java.lang.annotation.Retention(java.lang.annotation.RetentionPolicy.RUNTIME)
@java.lang.annotation.Documented
public @interface WebServlet {
    java.lang.String name() default "";

    java.lang.String[] value() default {};

    java.lang.String[] urlPatterns() default {};

    int loadOnStartup() default -1;

    javax.servlet.annotation.WebInitParam[] initParams() default {};

    boolean asyncSupported() default false;

    java.lang.String smallIcon() default "";

    java.lang.String largeIcon() default "";

    java.lang.String description() default "";

    java.lang.String displayName() default "";
}
```





## 6.Servlet的体系结构



​		   **Servlet       ---		接口**
​				|
**GenericServlet	---		抽象类**
​				|
​	   **HttpServlet   ---		抽象类**



### 1.Genericservlet : 将 Servlet接口中其他的方法做了默认空实现,只将 service() 方法作为抽象

* **将来定义 Servlet类时,可以继承 Genericservlet,实现 service()方法即可**

### 2.Httpservlet : 对http协议的一种封装,简化操作

* **1.定义类继承**
* **2.复写 doGet/ doPost方法**



```java
package com.itrs.web.servlet;

import javax.servlet.GenericServlet;
import javax.servlet.ServletException;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;
import javax.servlet.annotation.WebServlet;
import java.io.IOException;

@WebServlet("/demo3")
public class HttpServletDemo extends GenericServlet {
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException{
        System.out.println("demo3.....");
    }
}
```

```html
<form action="demo4" method="post">
    <input name="username">
    <input type="submit" value="提交">
</form>
```

```java
package com.itrs.web.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/demo4")
public class ServletDemo4 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("doGet......");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("doPost.....");
    }
}
```



## 7.Servlet相关配置



### 1.urlpartten：Servlet访问路径

* **1.一个Servlet可以定义多个访问路径：@WebServlet({"/d5","/dd5","/ddd5"})**

* **2.路径定义规则：**
	* **/xxx**
	* **/xxx/xxx : 多层路径，目录结构**
	* *.do

```java
package com.itrs.web.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

/**
 * Servlet路径配置
 */
//@WebServlet({"/d5","/dd5","/ddd5"})
//@WebServlet("/user/demo5")
//@WebServlet("/user/*")  /*  *是通配符，代表任意  */
//@WebServlet("/*")
@WebServlet("*.do")     /* 注：这里不能加/  */
public class ServletDemo5 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("demo5....");
    }
}
```



# 4.请求和响应

## Http协议

## 1.请求消息：

**客户端发送给服务器端的数据(数据格式)**

### 1.请求行

(https://www.bilibili.com/video/BV1qv4y1o79t?p=243&spm_id_from=pageDriver)

* **请求方式   请求url   请求协议/版本**
* **GET     /login.html     HTTP/1.1**



* **请求方式：**

	* **HTTP协议有7种请求方式，常用的有2种**

	* **GET：**

		* **1.请求参数在请求行中，在url后**
		* **2.请求的url长度有限制的**
		* **3.不太安全**

	* **POST：**

		* **1.请求参数在请求体中**
		* **2.请求的url长度没有限制的**
		* **3.相对安全**

		

### 2.请求头：

**客户端浏览器告诉服务器一些信息**

* **请求头名称：请求头值**

* **常见的请求头：**

#### 1.User-Agent：

**浏览器告诉服务器，我访问你使用的浏览器版本信息**

* **可以在服务器端获取该头的信息，解决浏览器的兼容性问题**

#### 2.Referer：

**http://localhost/login.html**

* **告诉服务器，我（当前请求）从哪里来?**
* **作用**
	* **1.防盗链：**
	* **2.统计工作：**



### 3.请求空行

* **空行，就是用于分割POST请求头，和请求体的**



### 4.请求体（正文）

* **封装POST请求消息的请求参数的**



### 5.字符串格式：

​		POST/login.html	HTTP/1.1
​		Host: localhost
​		User-agent: Mozilla/5. 0(Windows NT 6. 1; Win64; X64; rv: 60. 0)Gecko/20100101 **Firefox**/60.0
​		Accept: text/html, application/xhtml+xml, application/xml; q=0.9, "/;q=0.8
​		Accept-language: zh-cn, zh; q=0.8, zh-tw; q=0. 7, zh-hk; q=0.5, en-us; q=0.3, en; q=0.2
​		Accept-Encoding: gzip, deflate
​		Referer：http://localhost/login.html
​		Connection: keep-alive
​		Upgrade-insecure-requests: 1

​		username=zhangsan



## 2.响应式消息：

**服务器端发送给客户端的数据(数据格式)**

### 1.响应行

#### 1.组成：协议/版本  响应状态码 状态码描述

#### 2.响应状态码：服务器告诉客户端浏览器本次请求和响应的一个状态

* **1.状态码都是3位数字**
* **2.分类：**
	* **1XX：服务器就收客户端消息,但没有接受完成,等待一段时间后,发送1XX多状态码**
	* **2XX：成功。代表：200**
	* **3XX：重定向。代表：302（重定向），304（访问缓存）**
	* **4XX：客户端错误。**
	* **代表：**
		* **404（请求路径没有对应的资源）**
		* **405：请求方式没有对应的doXxx方法**
	* **5XX：服务器端错误**
	* **代表：**
		* **500（服务器内部出现异常）**



### 2.响应头：

#### 1.格式：头名称：值

#### 2.常见的响应头：

* **1.Content-Type:服务器告诉客户端本次响应体数据格式以及编码格式**
* **2.Content- disposition:服务器告诉客户端以什么格式打开响应体数据**
	* **值**
		* **in-line：默认值，在当前页面内打开**
		* **attachment；filename=xxx：以附件形式打开响应体。文件下载**



### 3.响应空行



### 4.响应体：传输的数据

* **响应字符串格式**

```html
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
Content-length: 101
Date: Wed. 06 Jun 2018 07: 08: 42 GMT
<html>
	<head>
		<title>$title$</title>
	</head>
	<body>
	hello, response
	</body>
</html>
```





## 3.Request

### 1.request对象和response对象的原理

* **1.request和response对象是由服务器创建的，我们使用**
* **2.request对象是来获取请求消息，response对象是来设置响应消息**



### 2.request对象继承体系结构：

* **ServletRequest		 	------		接口**
* ​            **|       继承**
* **HttpServletRequest    ------      接口**
* ​            **|        实现**
* **org.apache.catalina.connector.RequestFacade 类(Tomcat)**



### 3.request功能：



#### 1.获取请求消息数据

##### 	1.获取请求行数据

* **GET /myServlet/demo1?name=itrs HTTP/1.1**

* **方法**

* **1.获取请求方式：GET**

	* String  getMethod()

* **2.⭐获取虚拟目录：/myServlet**

	* String  getContextPath()

* **3.获取Servlet路径：/demo1**

	* String  getServletPath()

* **4.获取get方式请求参数：name = itrs**

	* String  getQueryString()

* **5.⭐获取请求URI：/myServlet/demo1**

	* String  getRequestURI():      /myServlet/demo1

	* StringBuffer  getRequestURL()     : http://localhost/myServlet/demo1

		 

	* URL：统一资源定位符： http://localhost/myServlet/demo1

		* 例：中华人民共和国

	* URI :   统一资源标识符：/myServlet/demo1

		* 例：共和国

* **6.获取协议及版本：HTTP/1.1**
	* String  getProtocol()
* **7.获取客户机的IP地址:**
	* String  getRemoteAddr()

###### *RequestDemo1

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

/**
 * 演示Request对象获取请求行数据
 */
@WebServlet("/requestDemo1")
public class RequestDemo1 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        /*
             1.获取请求方式：GET
                * String  getMethod()
             2.⭐获取虚拟目录：/myServlet
                * String  getContextPath()
             3.获取Servlet路径：/demo1
                * String  getServletPath()
             4.获取get方式请求参数：name = itrs
                * String  getQueryString()
             5.⭐获取请求URI：/myServlet/demo1
                * String  getRequestURI():      /myServlet/requestDemo1
                * StringBuffer  getRequestURL()     :http://localhost/myServlet/requestDemo1
             6.获取协议及版本：HTTP/1.1
                * String  getProtocol()
             7.获取客户机的IP地址:
                * String  getRemoteAddr()
         */
        
        //1.获取请求方式：GET
        String method = request.getMethod();
        System.out.println(method);

        //2.⭐获取虚拟目录：/myServlet
        String contextPath = request.getContextPath();
        System.out.println(contextPath);

        //3.获取Servlet路径：/demo1
        String servletPath = request.getServletPath();
        System.out.println(servletPath);

        //4.获取get方式请求参数：name = itrs
        String queryString = request.getQueryString();
        System.out.println(queryString);

        //5.⭐获取请求URI：/myServlet/demo1
        String requestURI = request.getRequestURI();
        StringBuffer requestURL = request.getRequestURL();
        System.out.println(requestURI);
        System.out.println(requestURL);

        //6.获取协议及版本：HTTP/1.1
        String protocol = request.getProtocol();
        System.out.println(protocol);

        //7.获取客户机的IP地址:
        String remoteAddr = request.getRemoteAddr();
        System.out.println(remoteAddr);

    }
}
```



##### 	2.获取请求头数据

* **方法：**
* **⭐String  getHeader(String  name): 通过请求头的名称获取请求头的值**
* **Enumeration<String>  getHeaderNames(): 获取所有的请求头名称**

###### *RequestDemo2

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.util.Enumeration;

@WebServlet("/requestDemo2")
public class RequestDemo2 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //演示获取请求头数据

        //1.获取所有请求头名称
        Enumeration<String> headerNames = request.getHeaderNames();
        //2.遍历
        while (headerNames.hasMoreElements()){
            String name = headerNames.nextElement();
            //根据名称获取请求头的值
            String value = request.getHeader(name);
            System.out.println(name+"-----"+value);
        }

    }
}
```

###### *RequestDemo3

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/requestDemo3")
public class RequestDemo3 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //演示获取请求头数据:user-agent

        String agent = request.getHeader("user-agent");
        //判断agent的浏览器版本
        if (agent.contains("Chrome")){
            //谷歌
            System.out.println("谷歌");
        }else if(agent.contains("Firefox")){
            //火狐
            System.out.println("火狐");
        }

    }
}
```

###### *RequestDemo4

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/requestDemo4")
public class RequestDemo4 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //演示获取请求头数据:referer

        String referer = request.getHeader("referer");
        System.out.println(referer);    //http://localhost/myServlet/login.html


        //防盗链
        if (referer != null) {
            if (referer.contains("/myServlet")) {
                //正常访问
                //System.out.println("播放电影....");
                /* 在网页上输出 */
                response.setContentType("text/html;charset=utf-8");
                response.getWriter().write("播放电影....");
            } else {
                //盗链
                //System.out.println("盗链");
                response.setContentType("text/html;charset=utf-8");
                response.getWriter().write("盗链....");
            }
        }

    }
}
```

##### 3.获取请求体数据

* **请求体：只有POST请求方式，才有请求体，在请求体中封装了POST请求的请求参数**
* **步骤**
* **1.获取流对象**
	* **BufferedReader  getReader(): 获取字符输入流，只能操作字符数据**
	* **ServletInputStream  getInputStream()：获取字节输入流，可以操作所有类型数据**
* **2.再从流对象中拿数据**



###### *regist.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>注册页面</title>
</head>
<body>
<form action="/myServlet/requestDemo5" method="post">
    <input type="text" placeholder="请输入用户名" name="username"><br>
    <input type="text" placeholder="请输入密码" name="password"><br>
    <input type="submit" value="注册">
</form>
</body>
</html>
```

###### *RequestDemo5

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.BufferedReader;
import java.io.IOException;

@WebServlet("/requestDemo5")
public class RequestDemo5 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //获取请求消息体---请求参数

        //1.获取字符流
        BufferedReader br = request.getReader();
        //2.读取数据
        String line = null;
        while ((line = br.readLine())!=null){
            System.out.println(line);
        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

    }
}
```



#### 2.其他功能

#####  1.获取请求参数通用方式:不论get还是post请求方式都可以使用下列方法来获取请求参数

* **1.String getParameter( String name):根据参数名称获取参数值 	username=itrs& password=123**

```html
<form action="/myServlet/requestDemo6" method="get">
    <input type="text" placeholder="请输入用户名" name="username"><br>
    <input type="text" placeholder="请输入密码" name="password"><br>
    <input type="submit" value="注册">
</form>
    regist2.html
```

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.BufferedReader;
import java.io.IOException;

@WebServlet("/requestDemo6")
public class RequestDemo6 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //post 获取请求参数

        //根据参数名称获取参数值
        String username = request.getParameter("username");
        System.out.println("post");
        System.out.println(username);
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //get 获取请求参数

        /*//根据参数名称获取参数值
        String username = request.getParameter("username");
        System.out.println("get");
        System.out.println(username);*/

        this.doPost(request,response);
    }
}
```



* **2.String[] getParameterValues( String name):根据参数名称获取参数值的数组     hob by=xx& hobby=game**

```html
<form action="/myServlet/requestDemo6" method="get">
    <input type="text" placeholder="请输入用户名" name="username"><br>
    <input type="text" placeholder="请输入密码" name="password"><br>

    <input type="checkbox" name="hobby" value="game">游戏
    <input type="checkbox" name="hobby" value="study">学习

    <input type="submit" value="注册">
</form>
```

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.BufferedReader;
import java.io.IOException;

@WebServlet("/requestDemo6")
public class RequestDemo6 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //post 获取请求参数

        //根据参数名称获取参数值
        String username = request.getParameter("username");

        //根据参数名称获取参数值的数组
        String[] hobbies = request.getParameterValues("hobby");
        for (String hobby:hobbies) {
            System.out.println(hobby);
        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //get 获取请求参数

        this.doPost(request,response);
    }
}
```



* **3. Enumeration< String> getParameterNames():获取所有请求的参数名称**

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.BufferedReader;
import java.io.IOException;
import java.util.Enumeration;

@WebServlet("/requestDemo6")
public class RequestDemo6 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //post 获取请求参数

        //根据参数名称获取参数值
        String username = request.getParameter("username");

        //根据参数名称获取参数值的数组
        String[] hobbies = request.getParameterValues("hobby");

        //获取所有请求的参数名称
        Enumeration<String> parameterNames = request.getParameterNames();
        while (parameterNames.hasMoreElements()){
            String name = parameterNames.nextElement();
            System.out.println(name);
            String value = request.getParameter(name);
            System.out.println(value);
            System.out.println("---------------------");
        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //get 获取请求参数

        this.doPost(request,response);
    }
}

/*
	username
    itrs
    ---------------------
    password
    123
    ---------------------
    hobby
    game
    ---------------------
    注：只返回一个包含请求消息中所有参数名称Enumeration对象
*/
```



* **4. Map<String, String[]> getParameterMap():获取所有参数的map集合**

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.BufferedReader;
import java.io.IOException;
import java.util.Enumeration;
import java.util.Map;
import java.util.Set;

@WebServlet("/requestDemo6")
public class RequestDemo6 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //post 获取请求参数

        //根据参数名称获取参数值
        String username = request.getParameter("username");

        //根据参数名称获取参数值的数组
        String[] hobbies = request.getParameterValues("hobby");
        
        //获取所有请求的参数名称
        Enumeration<String> parameterNames = request.getParameterNames();
        
        //获取所有参数的map集合
        Map<String, String[]> parameterMap = request.getParameterMap();
        //遍历
        Set<String> keyset = parameterMap.keySet();
        for (String name:keyset) {
            //获取键获取值
            String[] values = parameterMap.get(name);
            System.out.println(name);
            for (String value:values) {
                System.out.println(value);
            }
            System.out.println("------------");
        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //get 获取请求参数

        this.doPost(request,response);
    }
}

/*
	username
    itrs
    ------------
    password
    123
    ------------
    hobby
    game
    study
    ------------
	注：用于将请求消息中的所有参数名和值装进一个Map对象中放回
*/
```



* **中文乱码问题：------  RequestDemo7.java**
	* **get方式：tomcat 8 已经将 get 方式乱码的问题解决了**
	* **post方式：会乱码**
		* **解决：在获取参数前，设置request的编码：request.setCharacterEncoding("utf-8");**

##### 2.请求转发:  一种在服务器内部的资源跳转方式

###### 1.步骤：

* **1.通过 request对象获取请求转发器对象: Requestdispatcher getrequestdispatcher( String path)**
* **2.使用 RequestDispatcher对象来进行转发: forward( Servletrequest request, Servletresponse response)**

###### 2.特点：

* **1.浏览器地址栏路径不发生变化**
* **2.只能转发到当前服务器内部资源中**
* **3.转发是一次请求**

```java
package com.itrs.web.request;

import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/requestDemo8")
public class RequestDemo8 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo8被访问");
        //转发到demo9资源

//        RequestDispatcher requestDispatcher = request.getRequestDispatcher("/requestDemo9");
//        requestDispatcher.forward(request,response);

        //优化
        request.getRequestDispatcher("/requestDemo9").forward(request,response);
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/requestDemo9")
public class RequestDemo9 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo9被访问");
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```



##### 3.共享数据：

* **域对象：一个有作用范围的对象，可以在范围内共享数据**
* **request域：代表一次请求的范围，一般用于请求转发的多个资源共享数据**
* **方法：**
	* **1.void setAttribute( String name, object obj):存储数据**
	* **2.object getAttitude( string name):通过键获取值**
	* **3.void removeAttribute( String name):通过键移除键值对**

```java
package com.itrs.web.request;

import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/requestDemo8")
public class RequestDemo8 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("demo8被访问");
        //转发到demo9资源

//        RequestDispatcher requestDispatcher = request.getRequestDispatcher("/requestDemo9");
//        requestDispatcher.forward(request,response);

        //存储数据到request域中
        request.setAttribute("msg","hello");

        //优化
        request.getRequestDispatcher("/requestDemo9").forward(request,response);
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```

```java
package com.itrs.web.request;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/requestDemo9")
public class RequestDemo9 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //获取数据
        Object msg = request.getAttribute("msg");
        System.out.println(msg);

        System.out.println("demo9被访问");
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request,response);
    }
}
```

##### 4.获取 ServletContext

* **ServletContext getServletContext()**



## 🔺案例：用户登录

https://www.bilibili.com/video/BV1qv4y1o79t?p=257&spm_id_from=pageDriver

==注：部分知识未学到，先跳过==







## 4.Response对象

### 功能：设置响应式消息

#### 1.设置响应行

##### 1.格式：http/1.1  200  OK

##### 2.设置状态码：setStatus（int sc）

#### 2.设置响应头

**setHeader（String name,String value）**

#### 3.设置响应体

==**使用步骤：**==

* **1.获取输出流**
	* **字符输出流：PrintWriter getWriter()**
	* **字符输出流：ServletOutputStream getOutputStream()**
* **2.使用输出流，将数据输出到客户端浏览器**



### 案例：

#### 1.完成重定向

* **重定向：资源跳转的方式**

* **代码实现**

* ```java
	package cn.itrs.web.servlet;
	
	import javax.servlet.ServletException;
	import javax.servlet.annotation.WebServlet;
	import javax.servlet.http.HttpServlet;
	import javax.servlet.http.HttpServletRequest;
	import javax.servlet.http.HttpServletResponse;
	import java.io.IOException;
	
	/**
	 * 重定向
	 */
	
	@WebServlet("/responseDemo1")
	public class ResponseDemo1 extends HttpServlet{
	    @Override
	    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	        this.doPost(req,resp);
	    }
	
	    @Override
	    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	
	        System.out.println("demo1....");
	
	        //访问/responseDemo1,会自动跳转到/responseDemo资源
	        //1.设置状态码为302
	//        resp.setStatus(302);
	        //2.设置响应头location
	//        resp.setHeader("location","/responseDemo2");
	
	        //简单的重定向方法
	        resp.sendRedirect("/responseDemo2");
	    }
	}
	```

	```java
	package cn.itrs.web.servlet;
	
	import javax.servlet.ServletException;
	import javax.servlet.annotation.WebServlet;
	import javax.servlet.http.HttpServlet;
	import javax.servlet.http.HttpServletRequest;
	import javax.servlet.http.HttpServletResponse;
	import java.io.IOException;
	
	
	@WebServlet("/responseDemo2")
	public class ResponseDemo2 extends HttpServlet{
	    @Override
	    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	        this.doPost(req,resp);
	    }
	
	    @Override
	    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	        System.out.println("demo222222222......");
	    }
	}
	```



* **重定向的特点：redirect **

	* **1.地址栏发生变化**

	* **2.重定向可以访问其他站点（服务器）的资源**

	* ```java
		//简单的重定向方法
		//        resp.sendRedirect("/responseDemo2");
		        resp.sendRedirect("http://www.gitee.com");
		```

	* **3.重定向是俩次请求，不能使用request对象来共享数据**

* **转发的特点：forward **

	* **1.转发地址栏路径不变**
	* **2.转发只能访问当前服务器下的资源**
	* **3.转发是一次请求，可以使用request对象来共享数据**

#### 🔺面试题：forward 和 redirect 区别

* **路径写法：**
	* **1.相对路径：通过相对路径不可以确定唯一资源**
		* **如：./index.html**
		* **不以/开头， 以  . 开头路径**
		* **规则：找到当前资源和目标资源之间的相对位置关系**
			* **./：当前目录**
			* **../：后退一级目录**
	* **2.绝对路径：通过绝对路径可以确定唯一资源**
		* **以/开头的路径**
		* **规则：判断定义的路径是给谁用的？判断请求将来从哪里发出**
			* **给客户端浏览器使用：需要加虚拟目录（项目的访问路径）**
				* **建议虚拟目录动态获取：req.getContextPath()**
				* **<a>,<form> 重定向...**
			* **给服务器使用：不需要加虚拟目录**
				* **转发路径**

```java
package cn.itrs.web.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;


@WebServlet("/responseDemo3")
public class ResponseDemo3 extends HttpServlet{
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doPost(req,resp);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //转发
        req.getRequestDispatcher("/responseDemo2").forward(req,resp);
    }
}
```



#### 2.服务器输出字符数据到浏览器

* **步骤：**

	* **1.获取字符输出流**
	* **2.输出数据**

* **注意：**

	* **乱码问题：**

		* **1.PrintWriter pw = resp.getWriter();  获取的流的默认编码是ISO-8859-1**

		* **2.设置该流的默认编码**

		* **3.告诉浏览器响应体使用的编码**

		* ```java
			//简单的形式，设置编码
			resp.setContentType("text/html;charset=utf-8");
			```

```java
package cn.itrs.web.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.io.PrintWriter;


@WebServlet("/responseDemo4")
public class ResponseDemo4 extends HttpServlet{
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doPost(req,resp);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取流对象之前，设置流的默认编码：ISO-8859-1 设置为：GBK
//        resp.setCharacterEncoding("GBK");

        // 告诉浏览器，服务器发送的消息体数据的编码，建议浏览器使用该编码解码
//        resp.setHeader("content-type","text/html;charset=utf-8");

        //简单的形式，设置编码
        resp.setContentType("text/html;charset=utf-8");

        //1.获取字符输出流
        PrintWriter pw = resp.getWriter();
        //2.输出数据
//        pw.write("<h1>hello response</h1>");
        pw.write("<h1>输出数据</h1>");

    }
}
```



#### 3.服务器输出字节数据到浏览器

* **步骤：**

	* **1.获取字节输出流**
	* **2.输出数据**

* ```java
	package cn.itrs.web.servlet;
	
	import javax.servlet.ServletException;
	import javax.servlet.ServletOutputStream;
	import javax.servlet.annotation.WebServlet;
	import javax.servlet.http.HttpServlet;
	import javax.servlet.http.HttpServletRequest;
	import javax.servlet.http.HttpServletResponse;
	import java.io.IOException;
	
	
	@WebServlet("/responseDemo5")
	public class ResponseDemo5 extends HttpServlet{
	    @Override
	    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	        this.doPost(req,resp);
	    }
	
	    @Override
	    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	        resp.setContentType("text/html;charset=utf-8");
	
	        //1.获取字节输出流
	        ServletOutputStream sos = resp.getOutputStream();
	        //2.输出数据
	        sos.write("你好".getBytes("utf-8"));
	    }
	}
	```

	

#### 4.验证码

* **1.本质：图片**

* **2.目的：防止恶意表单注册**

* ```java
	package cn.itrs.web.servlet;
	
	import javax.imageio.ImageIO;
	import javax.servlet.ServletException;
	
	import javax.servlet.annotation.WebServlet;
	import javax.servlet.http.HttpServlet;
	import javax.servlet.http.HttpServletRequest;
	import javax.servlet.http.HttpServletResponse;
	import java.awt.*;
	import java.awt.image.BufferedImage;
	import java.io.IOException;
	import java.util.Random;
	
	
	@WebServlet("/checkCodeServlet")
	public class checkCodeServerlet extends HttpServlet{
	    @Override
	    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	        this.doPost(req,resp);
	    }
	
	    @Override
	    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
	        int width = 100;
	        int height = 50;
	
	        //1.创建一对象，在内存中图片（验证码图片对象）
	        BufferedImage image = new BufferedImage(width,height,BufferedImage.TYPE_INT_RGB);
	        //2.美化图片
	        //2.1填充背景色
	        Graphics g = image.getGraphics();//画笔对象
	        g.setColor(Color.PINK);//设置画笔颜色
	        g.fillRect(0,0,width,height);
	
	        //2.2画边框
	        g.setColor(Color.BLUE);
	        g.drawRect(0,0,width-1,height-1);
	
	        String str = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
	        //生成随机角标
	        Random random = new Random();
	        for (int i = 1; i <=4 ; i++) {
	            int index = random.nextInt(str.length());
	            //获取字符
	            char ch = str.charAt(index);//随机字符
	            // 2.3写验证码
	            g.drawString(ch+"",width/5*i,height/2);
	        }
	
	        //2.4画干扰线
	        g.setColor(Color.green);
	        //随机生成坐标点
	        for (int i = 0; i <10 ; i++) {
	            int x1 = random.nextInt(width);
	            int x2 = random.nextInt(width);
	
	            int y1 = random.nextInt(height);
	            int y2 = random.nextInt(height);
	            g.drawLine(x1,y1,x2,y2);
	        }
	
	        //3.将图片输出到页面展示
	        ImageIO.write(image,"jpg",resp.getOutputStream());
	    }
	}
	```

	```html
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <title>Title</title>
	    <script>
	        /*
	            分析：
	            点击超链接或者图片，换一张
	            1.给超链接和图片绑定单击时间
	
	            2.重新设置图片的src属性值
	         */
	        window.onload = function (ev) {
	            //1.获取图片对象
	            var img = document.getElementById("checkCode");
	            //2.绑定单击事件
	            img.onclick = function (ev1) {
	                //加时间戳
	                var date = new Date().getTime();
	
	                img.src = "/checkCodeServlet?"+date;
	            }
	
	            var on = document.getElementById("change");
	            on.onclick = function (ev1) {
	                // var date = new Date().getTime();
	                // on.href = "";
	            }
	        }
	    </script>
	</head>
	<body>
	<img id="checkCode" src="/checkCodeServlet"/>
	<a id="change" href="">看不清换一张？</a>
	</body>
	</html>
	```

	



## 5.ServletContext对象

### 1.概念：

==**代表整个web应用，可以和程序的容器（服务器）来通信**==

### 2.获取：

#### 1.通过request对象获取

==**req.getServletContext();**==

#### 2.通过HttpServlet获取

==**this.getServletContext();**==

```java
package cn.itrs.web.servlet;

import javax.servlet.ServletContext;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/servletContextDemo1")
public class ServletContextDemo1 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*
        ServletContext对象获取：
            1.通过request对象获取
                req.getServletContext();
            2.通过HttpServlet获取
                this.getServletContext();
         */

        //1.通过request对象获取
        ServletContext context1 = req.getServletContext();
        //2.通过HttpServlet获取
        ServletContext context2 = this.getServletContext();

        System.out.println(context1);
        System.out.println(context2);

        System.out.println(context1==context2);//true
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doGet(req,resp);
    }
}
```

### 2.功能：

#### 1.获取：MIME类型：

* **MIME类型：在互联网通信过程中定义的一种文件数据类型**
	* **格式：大类型/小类型   text/html    image/jpeg**
* **获取：String getMimeType(String file)**

```java
package cn.itrs.web.servletcontext;

import javax.servlet.ServletContext;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/servletContextDemo2")
public class ServletContextDemo2 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*
        ServletContext功能：
           1.获取：MIME类型：
                MIME类型：在互联网通信过程中定义的一种文件数据类型
	                格式：大类型/小类型   text/html    image/jpeg
                获取：String getMimeType(String file)
            2.域对象：共享数据
            3.获取文件的真实（服务器）路径
         */


        //2.通过HttpServlet获取
        ServletContext context = this.getServletContext();

        //3.定义文件名称
        String filename = "a.jpg";//image/jpeg

        //4.获取MIME类型
        String mimeType = context.getMimeType(filename);
        System.out.println(mimeType);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doGet(req,resp);
    }
}
```



#### 2.域对象：共享数据

* **1.setAttribute(String name,Object value)**
* **2.getAttribute(String name)**
* **3.removeAttribute(String name)**
* **ServletContext对象范围：所有用户所有请求的数据**

```java
package cn.itrs.web.servletcontext;

import javax.servlet.ServletContext;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/servletContextDemo3")
public class ServletContextDemo3 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*
        ServletContext功能：
           1.获取：MIME类型：
            2.域对象：共享数据
            3.获取文件的真实（服务器）路径
         */


        //2.通过HttpServlet获取
        ServletContext context = this.getServletContext();

        //设置数据
        context.setAttribute("msg","haha");

        //3.定义文件名称
        String filename = "a.jpg";//image/jpeg

        //4.获取MIME类型
        String mimeType = context.getMimeType(filename);
        System.out.println(mimeType);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doGet(req,resp);
    }
}
```

```java
package cn.itrs.web.servletcontext;

import javax.servlet.ServletContext;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/servletContextDemo4")
public class ServletContextDemo4 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*
        ServletContext功能：
           1.获取：MIME类型：
            2.域对象：共享数据
            3.获取文件的真实（服务器）路径
         */


        //2.通过HttpServlet获取
        ServletContext context = this.getServletContext();

        //获取数据
        Object msg = context.getAttribute("msg");
        System.out.println(msg);

        //3.定义文件名称
        String filename = "a.jpg";//image/jpeg

        //4.获取MIME类型
        String mimeType = context.getMimeType(filename);
        System.out.println(mimeType);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doGet(req,resp);
    }
}
```



#### 3.获取文件的真实（服务器）路径

* **方法：String getRealPath(String path)**

```java
package cn.itrs.web.servletcontext;

import javax.servlet.ServletContext;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/servletContextDemo4")
public class ServletContextDemo5 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        /*
        ServletContext功能：
           1.获取：MIME类型：
            2.域对象：共享数据
            3.获取文件的真实（服务器）路径
         */
        
        //2.通过HttpServlet获取
        ServletContext context = this.getServletContext();

        //获取文件的服务器路径
        String realPath = context.getRealPath("/b.txt");//web目录下资源访问
        System.out.println(realPath);

        String c = context.getRealPath("/WEB-INF/c.txt");//WEB-INF 目录下的资源访问
        System.out.println(c);

        String a = context.getRealPath("/WEB-INf/classes/a.txt");//src目录下的资源访问
        System.out.println(a);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doGet(req,resp);
    }
}
```



## 6.案例：

[黑马程序员JavaWeb全套基础教程，Java Web从入门到项目实战（IDEA版）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1qv4y1o79t?p=282&spm_id_from=pageDriver)

### 1.文件下载需求：

#### 1.页面显示超链接

#### 2.点击超链接后弹出下载提示框

#### 3.完成图片文件下载



# 5.会话及其会话技术

## 1.会话技术

### 1.会话概述：

==**一次会话中包含多次请求和响应**==

* **一次会话：浏览器第一次给服务器资源发送请求，会话建立，知道有一方断开为止**

### 2.功能：

==**在一次会话的范围内的多次请求间，共享数据**==

### 3.方式：

#### 1.客户端会话技术：Cookie

#### 2.服务器端会话技术：Session

 

## 2.Cookie：

### 1.概念：客户端会话技术，将数据保存到客户端



### 2.快速入门：

#### 1.使用步骤：

* **1.创建Cookie对象，绑定数据**
	* ==**new Cookie(String name,String value)**==
* **2.发送Cookie对象**
	* ==**response.addCookie(Cookie cookie)**==
* **3.获取Cookie，拿到数据**
	* ==**Cookie[ ] request.getCookies()**==

```java
package cn.itrs.cookie;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

/**
 * Cookie快速入门
 */
@WebServlet("/cookieDemo1")
public class CookieDemo1 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.创建Cookie对象
        Cookie c = new Cookie("msg","hello");
        //2.发送Cookie
        response.addCookie(c);
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```

```java
package cn.itrs.cookie;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/cookieDemo2")
public class CookieDemo2 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //3.获取Cookie
        Cookie[] cs = request.getCookies();
        //获取数据，遍历Cookies
        if (cs != null) {
            for (Cookie c : cs) {
                String name = c.getName();
                String value = c.getValue();
                System.out.println(name+":"+value);
            }
        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```



## 3.实现原理

==**基于响应头set-cookie和请求头Cookie实现**==

## 4.Cookie的细节

### 1.一次可不可以发送多个cookie？

* **可以**
* **可以创建多个Cookie对象，使用response调用多次add Cookie方式发送cookie即可**

### 2.cookie在浏览器中保存多长时间？

#### 1.默认情况下，当浏览器关闭后，Cookie数据被销毁

#### 2.持久化存储：

* **setMaxAge(int seconds)**
	* **1.正数：将Cookie数据写到硬盘的文件中。持久化存储。Cookie存活时间。**
	* **2.负数：默认值**
	* **3.零：删除Cookie信息**

```java
package com.itrs;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/cookieDemo4")
public class CookieDemo4 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.创建Cookie对象
        Cookie c1 = new Cookie("msg","itrs");
        //2.设置cookie的存活时间
//        c1.setMaxAge(30);//将cookie持久化到硬盘，30秒后会自动删除cookie文件
//        c1.setMaxAge(-1);
        c1.setMaxAge(0);//删除
//        c1.setMaxAge(300);
        //3.发送Cookie
        response.addCookie(c1);

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```



### 3.cookie能不能存中文？

* **在tomcat 8 前 cookie中不能直接存储中文数据**
	* **需要将中文数据转码----一般采用URL编码（%E3）**
* **在tomcat 8 后 cookie支持中文数据。特殊字符还是不支持，建议使用URL编码存储，URL编码解析**

```java
package com.itrs;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/cookieDemo5")
public class CookieDemo5 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.创建Cookie对象
        Cookie c1 = new Cookie("msg","你好");

        //3.发送Cookie
        response.addCookie(c1);

    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```

==访问cookieDemo5后再访问cookieDemo2==

### 4.cookie共享问题？

#### 1.假设在一个 tomcat服务器中,部署了多个web项目,那么在这些web项目中 cookies能不能共享?

* **默认情况下 cookie不能共享**

* **setPath(String  path)：设置Cookie的获取范围。默认情况下，设置当前的虚拟目录**

	* **如果要共享，则可以将 path 设置为 "/"**

	```java
	package com.itrs;
	
	import javax.servlet.ServletException;
	import javax.servlet.annotation.WebServlet;
	import javax.servlet.http.Cookie;
	import javax.servlet.http.HttpServlet;
	import javax.servlet.http.HttpServletRequest;
	import javax.servlet.http.HttpServletResponse;
	import java.io.IOException;
	
	@WebServlet("/cookieDemo5")
	public class CookieDemo5 extends HttpServlet {
	    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        //1.创建Cookie对象
	        Cookie c1 = new Cookie("msg","你好");
	        //设置 path ，让当前服务器下部署的所有项目共享 Cookie 信息
	        c1.setPath("/");
	        //3.发送Cookie
	        response.addCookie(c1);
	
	    }
	
	    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
	        this.doPost(request, response);
	    }
	}
	```

#### 2.不同的tomcat 服务器间cookie共享问题？

* **setDomain(String  path)：如果设置一级域名相同，那么多个服务器之间cookie可以共享**
	* **setDomain（".baidu.com"）, 那么tieba.baidu.com和new.baidu.com中cookie可以共享**



## 5.Cookie的特点和作用

### 1.cookie存储数据再客户端浏览器

### 2.浏览器对于单个cookie的大小有限制（4kb）以及对同一个域名下的总cookie数量也有限制（20个）

### 3.作用：

#### 1.cookie一般用于存储少量的不太敏感的数据

#### 2.在不登录的情况下，完成服务器对客户端的身份识别



## 6.案例：记住上一次访问时间

### 1.需求：

#### 1.访问个 Servlet,如果是第一次访问,则提示:您好,欢迎您首次访问。

#### 2.如果不是第一次访问,则提示:欢迎回来,您上次访问时间为:显示时间字符串



### 2.分析：

#### 1.可以采用Cookie来完成

#### 2.在服务器中的 Servlet 判断是否有一个名为 lastTime 的 Cookie

* **1.有：不是第一次访问**
	* **1.响应数据：欢迎回来，你上次访问时间为：xxxx年xx月xx日xx:xx:xx**
	* **2.写回Cookie：lastTime = xxxx年x月xx日 xx:xx:xx**
* **2.，没有：是第一次访问**
	* **1.响应数据：您好，欢迎您首次访问**
	* **2.写回Cookie：lastTime =  xxxx年x月xx日 xx:xx:xx**



```java
package com.itrs;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.net.URLDecoder;
import java.net.URLEncoder;
import java.text.SimpleDateFormat;
import java.util.Date;

/**
  在服务器中的 Servlet 判断是否有一个名为 lastTime 的 Cookie
 * 1.有：不是第一次访问**
    **1.响应数据：欢迎回来，你上次访问时间为：yyyy年MM月dd日 HH:mm:ss
    **2.写回Cookie：lastTime = yyyy年MM月dd日 HH:mm:ss
 * 2.，没有：是第一次访问**
    **1.响应数据：您好，欢迎您首次访问**
    **2.写回Cookie：lastTime =  yyyy年MM月dd日 HH:mm:ss
 */
@WebServlet("/cookieDemo")
public class CookieDemo extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //设置响应的消息体的数据格式以及编码
        response.setContentType("test/html;charset=utf-8");
        //1.获取所有Cookie
        Cookie[] cookies = request.getCookies();
        boolean flag = false;//没有cookie为lastTime
        //2.遍历Cookie数组
        if (cookies != null && cookies.length>0){
            for (Cookie cookie:cookies){
                //3.获取cookie的名称
                String name = cookie.getName();
                //4.判断名称是否是：lastTime
                if ("lastTime".equals(name)){
                    //有该Cookie，不是第一次访问

                    flag = true;//有lastTime的cookie

                    //设置Cookie的value
                    //获取当前时间的字符串，重新设置Cookie的值，重新发送Cookie
                    Date date = new Date();
                    SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
                    String str_date = sdf.format(date);
                    System.out.println("编码前："+str_date);
                    //URL 编码
                    str_date = URLEncoder.encode(str_date, "UTF-8");
                    System.out.println("编码后："+str_date);
                    cookie.setValue(str_date);
                    //设置cookie的存活时间
                    cookie.setMaxAge(60*60*24*30);//一个月
                    response.addCookie(cookie);

                    //响应数据
                    //获取Cookie的value，时间
                    String value = cookie.getValue();
                    System.out.println("解码前："+value);
                    //URL解码：
                    value = URLDecoder.decode(value,"UTF-8");
                    System.out.println("解码后："+value);
                    response.getWriter().write("<h1>欢迎回来，您上次访问时间为："+value+"</h1>");

                    break;
                }
            }
        }

        if (cookies == null || cookies.length == 0 || flag == false){
            //第一次访问

            //设置Cookie的value
            //获取当前时间的字符串，重新设置Cookie的值，重新发送Cookie
            Date date = new Date();
            SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
            String str_date = sdf.format(date);
            System.out.println("编码前："+str_date);
            //URL 编码
            str_date = URLEncoder.encode(str_date, "UTF-8");
            System.out.println("编码后："+str_date);
            Cookie cookie = new Cookie("lastTime",str_date);
            //设置cookie的存活时间
            cookie.setMaxAge(60*60*24*30);//一个月
            response.addCookie(cookie);

            response.getWriter().write("<h1>欢迎您首次访问</h1>");

        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```

==可能有错==



## 7.Session

### 1.概念:

**服务器端会话技术,在一次会话的多次请求间共享数据,将数据保存在服务器端的对家中。 Httpsession**

### 2.快速入门:

#### 1.获取HttpSession对象：

```java
HttpSession session = req.getSession();
```

```java
package com.session;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;
import java.io.IOException;

@WebServlet("/sessionDemo1")
public class SessionDemo1 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //使用session共享数据

        //1.获取session
        HttpSession session = req.getSession();
        //2.存储数据
        session.setAttribute("msg","hello session");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doPost(req, resp);
    }
}
```

#### 2.使用HttpSession对象：

* **object getattribute(String name)**
* **void setattribute(String name, Object value)**
* **void removeattribute(String name)**

```java
package com.session;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;
import java.io.IOException;

@WebServlet("/sessionDemo2")
public class SessionDemo2 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //使用session共享数据

        //1.获取session
        HttpSession session = req.getSession();
        //2.存储数据
        Object msg = session.getAttribute("msg");
        System.out.println(msg);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doPost(req, resp);
    }
}
```

### 3.原理

**Seesion 的实现是依赖于Cookie的**



### 4.细节：

#### 1.当客户端关闭后，服务器不关闭，两次获取Session是否为同一个？

* **默认情况下，不是**
* **如果需要相同，则可以创建Cookie，键位JSESSIONID，设置最大存活时间，让Cookie持久化保存。**

```java
package com.session;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;
import java.io.IOException;

@WebServlet("/sessionDemo3")
public class SessionDemo3 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {

        //1.获取session
        HttpSession session = req.getSession();
        //期望客户端关闭后：session也能相同
        Cookie c = new Cookie("JSESSIONID",session.getId());
        c.setMaxAge(60*60); //一小时内session为同一个
        resp.addCookie(c);

        System.out.println(session);

    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        this.doPost(req, resp);
    }
}
```

#### 2.客户端不关闭后，服务器关闭后，两次获取Session是同一个吗？

* **不是同一个，但是要确保数据不丢失**
	* **session的钝化：**
		* **在服务器正常关闭之前，将session对象系列化到硬盘上**
	* **session的活化：**
		* **在服务器启动后，将session文件转化为内存中的session对象即可。**



#### 3.session 的失效时间？

