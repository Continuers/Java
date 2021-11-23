# 6.Servlet高级

## 1.Filter：过滤器

### 1.概念

* **web中的过滤器：当访问服务器的资源时，过滤器可以将请求拦截下来，完成一些特殊的功能**
* **过滤器的作用：**
	* **一般用于完成通用的操作。如: 登录验证，统一编码处理、敏感字符过滤。。。**



### 2.快速入门：

#### 1.步骤：

##### 1.定义一个类，实现接口Filter

##### 2.复写方法

##### 3.配置拦截路径

* **1.web.xml**
* **2.注解**

```Java
package com.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

/**
 * 过滤器快速入门程序
 */
@WebFilter("/*")//访问所有资源之前，都会执行该过滤器
public class FilterDemo1 implements Filter {
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {

    }

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("filterDemo1被执行了...");

        //放行
        filterChain.doFilter(servletRequest, servletResponse);
    }

    @Override
    public void destroy() {

    }
}
```

### 3.过滤器细节：

#### 1.web.xml配置

```xml
<filter>
    <filter-name>demo1</filter-name>
    <filter-class>com.filter.FilterDemo1</filter-class>
</filter>
<filter-mapping>
    <filter-name>demo1</filter-name>
    <!--拦截路径-->
    <url-pattern>/*</url-pattern>
</filter-mapping>
```

#### 2.过滤器执行流程

##### 1.执行过滤器

##### 2.执行放行后的资源

##### 3.回来执行过滤器放行代码下边的代码

```java
package com.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

@WebFilter("/*")
public class FilterDemo2 implements Filter {
    public void destroy() {
    }

    public void doFilter(ServletRequest req, ServletResponse resp, FilterChain chain) throws ServletException, IOException {
        //对request对象请求消息增强
        System.out.println("filterDemo2执行了....");
        //放行
        chain.doFilter(req, resp);
        //对response对象的响应消息增强
        System.out.println("filterDemo2回来了....");
    }

    public void init(FilterConfig config) throws ServletException {

    }
}
```



#### 3.过滤器生命周期方法

##### 1.init：在服务器启动后，会创建Filter对象，然后调用init方法。只执行一次，用于加载资源

##### 2.doFilter：每一次请求被拦截资源时，会执行，执行多次

##### 3.destroy：在服务器关闭后，Filter对象被销毁，如果服务器时正常关闭，则会执行destroy方法。只执行一次。用于释放资源

```java
package com.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

@WebFilter("/*")
public class FilterDemo3 implements Filter {
    /**
     * 在服务器关闭后，Filter对象被销毁，如果服务器时正常关闭，则会执行destroy方法。只执行一次。用于释放资源
     */
    public void destroy() {
        System.out.println("destroy...");
    }

    /**
     * 每一次请求被拦截资源时，会执行，执行多次
     * @param req
     * @param resp
     * @param chain
     * @throws ServletException
     * @throws IOException
     */
    public void doFilter(ServletRequest req, ServletResponse resp, FilterChain chain) throws ServletException, IOException {
        System.out.println("doFilter...");
        chain.doFilter(req, resp);
    }

    /**
     *在服务器启动后，会创建Filter对象，然后调用init方法。只执行一次，用于加载资源
     * @param config
     * @throws ServletException
     */
    public void init(FilterConfig config) throws ServletException {
        System.out.println("init.....");
    }

}
```



####  4.过滤器配置详解

##### 1.拦截路径配置：

* **1.具体资源路径：/ index.jsp   只有访问 index.jsp资源时,过滤器才会被执行**
* **2.拦截目录:       /user/*      访问/user下的所有资源时，过滤器都会被执行**
* **3.后缀名拦截: *.jsp         访问所有后缀名为jsp资源时，过滤器都会被执行**
* **4.拦截所有资源; /*       访问所有资源时，过滤器都会被执行**

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>Title</title>
</head>
<body>
hello.jsp....
</body>
</html>
```

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
  <head>
    <title>$Title$</title>
  </head>
  <body>
index.jsp.....

  <%
    System.out.println("index.jsp...");
  %>
  </body>
</html>
```

```java
package com.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/user/findAllServlet")
public class ServletDemo1 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("findAllServlet....");
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```

```java
package com.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/user/updateServlet")
public class ServletDemo2 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("updateServlet....");
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```

```java
package com.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

//@WebFilter("/index.jsp")//1.具体资源路径：/ index.jsp   只有访问 index.jsp资源时,过滤器才会被执行
//@WebFilter("/user/*")//2.拦截目录: /user/*  访问/user下的所有资源时，过滤器都会被执行
@WebFilter("*.jsp")//3.后缀名拦截: *.jsp   访问所有后缀名为jsp资源时，过滤器都会被执行
public class FilterDemo4 implements Filter {
    public void destroy() {
    }

    public void doFilter(ServletRequest req, ServletResponse resp, FilterChain chain) throws ServletException, IOException {
        System.out.println("filterDemo4....");
        chain.doFilter(req, resp);
    }

    public void init(FilterConfig config) throws ServletException {

    }

}
```

##### 2.拦截方式配置：资源被访问的方式

* **注解配置：**
	* **设置dispatcherTypes属性**
		* **1.REQUEST: 默认值。浏览器直接请求资源**
		* **2.FORWARD: 转发访问资源**
		* **3.INCLUDE: 包含访问资源**
		* **4.ERROR: 错误跳转资源**
		* **5.ASYNC: 异步访问资源**

```java
package com.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/user/updateServlet")
public class ServletDemo2 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("updateServlet....");

        //转发到index.jsp
        request.getRequestDispatcher("/index.jsp").forward(request,response);
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```

```java
package com.filter;

import javax.servlet.*;
import javax.servlet.annotation.WebFilter;
import java.io.IOException;

//浏览器直接请求index.jsp资源时，该过滤器会被执行
//@WebFilter(value = "/index.jsp",dispatcherTypes = DispatcherType.REQUEST)
//只有转发访问index.jsp时，该过滤器才会被执行
//@WebFilter(value = "/index.jsp",dispatcherTypes = DispatcherType.FORWARD)
//浏览器直接请求index.jsp或者转发访问index.jsp。该过滤器才会被执行
@WebFilter(value = "/index.jsp",dispatcherTypes = {DispatcherType.FORWARD,DispatcherType.REQUEST})
public class FilterDemo5 implements Filter {
    public void destroy() {
    }

    public void doFilter(ServletRequest req, ServletResponse resp, FilterChain chain) throws ServletException, IOException {
        System.out.println("finterDemo5...");
        chain.doFilter(req, resp);
    }

    public void init(FilterConfig config) throws ServletException {

    }

}
```



* **web.xml配置**

```xml
<dispatcher></dispatcher>
```



#### 5.过滤器链(配置多个过滤器)


