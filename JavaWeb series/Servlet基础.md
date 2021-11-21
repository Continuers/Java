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

