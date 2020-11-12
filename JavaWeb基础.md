* [Java Web 基础](#java-web-%E5%9F%BA%E7%A1%80)
  * [一、JDBC 技术](#%E4%B8%80jdbc-%E6%8A%80%E6%9C%AF)
    * [1、说下原生 jdbc 操作数据库流程？](#1%E8%AF%B4%E4%B8%8B%E5%8E%9F%E7%94%9F-jdbc-%E6%93%8D%E4%BD%9C%E6%95%B0%E6%8D%AE%E5%BA%93%E6%B5%81%E7%A8%8B)
      * [1）加载驱动](#1%E5%8A%A0%E8%BD%BD%E9%A9%B1%E5%8A%A8)
      * [2）获取连接对象](#2%E8%8E%B7%E5%8F%96%E8%BF%9E%E6%8E%A5%E5%AF%B9%E8%B1%A1)
      * [3）根据 SQL 获取 sql 会话对象](#3%E6%A0%B9%E6%8D%AE-sql-%E8%8E%B7%E5%8F%96-sql-%E4%BC%9A%E8%AF%9D%E5%AF%B9%E8%B1%A1)
    * [2、为什么要用 PreparedStatement？](#2%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E7%94%A8-preparedstatement)
    * [3、关系数据库中连接池的机制是什么？](#3%E5%85%B3%E7%B3%BB%E6%95%B0%E6%8D%AE%E5%BA%93%E4%B8%AD%E8%BF%9E%E6%8E%A5%E6%B1%A0%E7%9A%84%E6%9C%BA%E5%88%B6%E6%98%AF%E4%BB%80%E4%B9%88)
      * [前提](#%E5%89%8D%E6%8F%90)
      * [1）从连接池获取或创建可用连接](#1%E4%BB%8E%E8%BF%9E%E6%8E%A5%E6%B1%A0%E8%8E%B7%E5%8F%96%E6%88%96%E5%88%9B%E5%BB%BA%E5%8F%AF%E7%94%A8%E8%BF%9E%E6%8E%A5)
      * [2）使用完毕之后](#2%E4%BD%BF%E7%94%A8%E5%AE%8C%E6%AF%95%E4%B9%8B%E5%90%8E)
      * [3）在系统关闭前](#3%E5%9C%A8%E7%B3%BB%E7%BB%9F%E5%85%B3%E9%97%AD%E5%89%8D)
      * [4）能够处理无效连接](#4%E8%83%BD%E5%A4%9F%E5%A4%84%E7%90%86%E6%97%A0%E6%95%88%E8%BF%9E%E6%8E%A5)
      * [几个概念](#%E5%87%A0%E4%B8%AA%E6%A6%82%E5%BF%B5)
        * [最小连接数](#%E6%9C%80%E5%B0%8F%E8%BF%9E%E6%8E%A5%E6%95%B0)
        * [最大连接数](#%E6%9C%80%E5%A4%A7%E8%BF%9E%E6%8E%A5%E6%95%B0)
        * [如果最小连接数与最大连接数相差太大](#%E5%A6%82%E6%9E%9C%E6%9C%80%E5%B0%8F%E8%BF%9E%E6%8E%A5%E6%95%B0%E4%B8%8E%E6%9C%80%E5%A4%A7%E8%BF%9E%E6%8E%A5%E6%95%B0%E7%9B%B8%E5%B7%AE%E5%A4%AA%E5%A4%A7)
  * [二、http 协议](#%E4%BA%8Chttp-%E5%8D%8F%E8%AE%AE)
    * [1、http 的长连接和短连接](#1http-%E7%9A%84%E9%95%BF%E8%BF%9E%E6%8E%A5%E5%92%8C%E7%9F%AD%E8%BF%9E%E6%8E%A5)
    * [2、HTTP/1\.1 与 HTTP/1\.0 的区别](#2http11-%E4%B8%8E-http10-%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [1）可扩展性](#1%E5%8F%AF%E6%89%A9%E5%B1%95%E6%80%A7)
      * [2）缓存](#2%E7%BC%93%E5%AD%98)
      * [3）带宽优化](#3%E5%B8%A6%E5%AE%BD%E4%BC%98%E5%8C%96)
        * [HTTP/1\.0 中，存在一些浪费带宽的现象](#http10-%E4%B8%AD%E5%AD%98%E5%9C%A8%E4%B8%80%E4%BA%9B%E6%B5%AA%E8%B4%B9%E5%B8%A6%E5%AE%BD%E7%9A%84%E7%8E%B0%E8%B1%A1)
        * [HTTP/1\.1 中在请求消息中引入了 range 头域](#http11-%E4%B8%AD%E5%9C%A8%E8%AF%B7%E6%B1%82%E6%B6%88%E6%81%AF%E4%B8%AD%E5%BC%95%E5%85%A5%E4%BA%86-range-%E5%A4%B4%E5%9F%9F)
        * [HTTP/1\.1 加入了一个新的状态码 100（Continue）。](#http11-%E5%8A%A0%E5%85%A5%E4%BA%86%E4%B8%80%E4%B8%AA%E6%96%B0%E7%9A%84%E7%8A%B6%E6%80%81%E7%A0%81-100continue)
        * [节省带宽资源的一个非常有效的做法就是压缩要传送的数据](#%E8%8A%82%E7%9C%81%E5%B8%A6%E5%AE%BD%E8%B5%84%E6%BA%90%E7%9A%84%E4%B8%80%E4%B8%AA%E9%9D%9E%E5%B8%B8%E6%9C%89%E6%95%88%E7%9A%84%E5%81%9A%E6%B3%95%E5%B0%B1%E6%98%AF%E5%8E%8B%E7%BC%A9%E8%A6%81%E4%BC%A0%E9%80%81%E7%9A%84%E6%95%B0%E6%8D%AE)
      * [4）长连接](#4%E9%95%BF%E8%BF%9E%E6%8E%A5)
        * [HTTP/1\.0 规定浏览器与服务器只保持短暂的连接](#http10-%E8%A7%84%E5%AE%9A%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%8E%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%8F%AA%E4%BF%9D%E6%8C%81%E7%9F%AD%E6%9A%82%E7%9A%84%E8%BF%9E%E6%8E%A5)
        * [HTTP 1\.1 支持长连接（PersistentConnection）和请求的流水线（Pipelining）处理](#http-11-%E6%94%AF%E6%8C%81%E9%95%BF%E8%BF%9E%E6%8E%A5persistentconnection%E5%92%8C%E8%AF%B7%E6%B1%82%E7%9A%84%E6%B5%81%E6%B0%B4%E7%BA%BFpipelining%E5%A4%84%E7%90%86)
        * [HTTP 1\.1 还允许客户端不用等待上一次请求结果返回，就可以发出下一次请求](#http-11-%E8%BF%98%E5%85%81%E8%AE%B8%E5%AE%A2%E6%88%B7%E7%AB%AF%E4%B8%8D%E7%94%A8%E7%AD%89%E5%BE%85%E4%B8%8A%E4%B8%80%E6%AC%A1%E8%AF%B7%E6%B1%82%E7%BB%93%E6%9E%9C%E8%BF%94%E5%9B%9E%E5%B0%B1%E5%8F%AF%E4%BB%A5%E5%8F%91%E5%87%BA%E4%B8%8B%E4%B8%80%E6%AC%A1%E8%AF%B7%E6%B1%82)
      * [5）消息传递](#5%E6%B6%88%E6%81%AF%E4%BC%A0%E9%80%92)
        * [HTTP 消息中可以包含任意长度的实体](#http-%E6%B6%88%E6%81%AF%E4%B8%AD%E5%8F%AF%E4%BB%A5%E5%8C%85%E5%90%AB%E4%BB%BB%E6%84%8F%E9%95%BF%E5%BA%A6%E7%9A%84%E5%AE%9E%E4%BD%93)
        * [HTTP/1\.1 中引入了 Chunkedtransfer\-coding 来解决上面这个问题](#http11-%E4%B8%AD%E5%BC%95%E5%85%A5%E4%BA%86-chunkedtransfer-coding-%E6%9D%A5%E8%A7%A3%E5%86%B3%E4%B8%8A%E9%9D%A2%E8%BF%99%E4%B8%AA%E9%97%AE%E9%A2%98)
        * [在 HTTP/1\.0 中，有一个 Content\-MD5 的头域](#%E5%9C%A8-http10-%E4%B8%AD%E6%9C%89%E4%B8%80%E4%B8%AA-content-md5-%E7%9A%84%E5%A4%B4%E5%9F%9F)
      * [6）Host 头域](#6host-%E5%A4%B4%E5%9F%9F)
        * [在 HTTP1\.0 中认为每台服务器都绑定一个唯一的 IP 地址](#%E5%9C%A8-http10-%E4%B8%AD%E8%AE%A4%E4%B8%BA%E6%AF%8F%E5%8F%B0%E6%9C%8D%E5%8A%A1%E5%99%A8%E9%83%BD%E7%BB%91%E5%AE%9A%E4%B8%80%E4%B8%AA%E5%94%AF%E4%B8%80%E7%9A%84-ip-%E5%9C%B0%E5%9D%80)
        * [HTTP1\.1 的请求消息和响应消息都应支持 Host 头域，且请求消息中如果没有 Host 头域会报告一个错误（400 Bad Request）](#http11-%E7%9A%84%E8%AF%B7%E6%B1%82%E6%B6%88%E6%81%AF%E5%92%8C%E5%93%8D%E5%BA%94%E6%B6%88%E6%81%AF%E9%83%BD%E5%BA%94%E6%94%AF%E6%8C%81-host-%E5%A4%B4%E5%9F%9F%E4%B8%94%E8%AF%B7%E6%B1%82%E6%B6%88%E6%81%AF%E4%B8%AD%E5%A6%82%E6%9E%9C%E6%B2%A1%E6%9C%89-host-%E5%A4%B4%E5%9F%9F%E4%BC%9A%E6%8A%A5%E5%91%8A%E4%B8%80%E4%B8%AA%E9%94%99%E8%AF%AF400-bad-request)
      * [7）错误提示](#7%E9%94%99%E8%AF%AF%E6%8F%90%E7%A4%BA)
        * [HTTP/1\.0 中只定义了 16 个状态响应码，对错误或警告的提示不够具体](#http10-%E4%B8%AD%E5%8F%AA%E5%AE%9A%E4%B9%89%E4%BA%86-16-%E4%B8%AA%E7%8A%B6%E6%80%81%E5%93%8D%E5%BA%94%E7%A0%81%E5%AF%B9%E9%94%99%E8%AF%AF%E6%88%96%E8%AD%A6%E5%91%8A%E7%9A%84%E6%8F%90%E7%A4%BA%E4%B8%8D%E5%A4%9F%E5%85%B7%E4%BD%93)
        * [HTTP/1\.1 中新增了 24 个状态响应码](#http11-%E4%B8%AD%E6%96%B0%E5%A2%9E%E4%BA%86-24-%E4%B8%AA%E7%8A%B6%E6%80%81%E5%93%8D%E5%BA%94%E7%A0%81)
    * [3、http 常见的状态码有哪些？](#3http-%E5%B8%B8%E8%A7%81%E7%9A%84%E7%8A%B6%E6%80%81%E7%A0%81%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [4、GET 和 POST 的区别？](#4get-%E5%92%8C-post-%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [1）请求数据位置](#1%E8%AF%B7%E6%B1%82%E6%95%B0%E6%8D%AE%E4%BD%8D%E7%BD%AE)
        * [GET 请求的数据会附在 URL 之后](#get-%E8%AF%B7%E6%B1%82%E7%9A%84%E6%95%B0%E6%8D%AE%E4%BC%9A%E9%99%84%E5%9C%A8-url-%E4%B9%8B%E5%90%8E)
        * [POST 把提交的数据则放置在是 HTTP 包的包体中。](#post-%E6%8A%8A%E6%8F%90%E4%BA%A4%E7%9A%84%E6%95%B0%E6%8D%AE%E5%88%99%E6%94%BE%E7%BD%AE%E5%9C%A8%E6%98%AF-http-%E5%8C%85%E7%9A%84%E5%8C%85%E4%BD%93%E4%B8%AD)
      * [2）GET 方式提交的数据最多只能是 1024 字节，理论上 POST 没有限制，可传较大量的数据](#2get-%E6%96%B9%E5%BC%8F%E6%8F%90%E4%BA%A4%E7%9A%84%E6%95%B0%E6%8D%AE%E6%9C%80%E5%A4%9A%E5%8F%AA%E8%83%BD%E6%98%AF-1024-%E5%AD%97%E8%8A%82%E7%90%86%E8%AE%BA%E4%B8%8A-post-%E6%B2%A1%E6%9C%89%E9%99%90%E5%88%B6%E5%8F%AF%E4%BC%A0%E8%BE%83%E5%A4%A7%E9%87%8F%E7%9A%84%E6%95%B0%E6%8D%AE)
      * [3）POST 的安全性要比 GET 的安全性高](#3post-%E7%9A%84%E5%AE%89%E5%85%A8%E6%80%A7%E8%A6%81%E6%AF%94-get-%E7%9A%84%E5%AE%89%E5%85%A8%E6%80%A7%E9%AB%98)
    * [5、http 中重定向和请求转发的区别？](#5http-%E4%B8%AD%E9%87%8D%E5%AE%9A%E5%90%91%E5%92%8C%E8%AF%B7%E6%B1%82%E8%BD%AC%E5%8F%91%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [本质区别](#%E6%9C%AC%E8%B4%A8%E5%8C%BA%E5%88%AB)
        * [重定向特点](#%E9%87%8D%E5%AE%9A%E5%90%91%E7%89%B9%E7%82%B9)
        * [请求转发特点](#%E8%AF%B7%E6%B1%82%E8%BD%AC%E5%8F%91%E7%89%B9%E7%82%B9)
  * [三、Cookie 和 Session](#%E4%B8%89cookie-%E5%92%8C-session)
    * [1、Cookie 和 Session 的区别](#1cookie-%E5%92%8C-session-%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [Cookie](#cookie)
      * [Session](#session)
      * [Cookie 和 Session 的不同点](#cookie-%E5%92%8C-session-%E7%9A%84%E4%B8%8D%E5%90%8C%E7%82%B9)
        * [1）无论客户端做怎样的设置](#1%E6%97%A0%E8%AE%BA%E5%AE%A2%E6%88%B7%E7%AB%AF%E5%81%9A%E6%80%8E%E6%A0%B7%E7%9A%84%E8%AE%BE%E7%BD%AE)
        * [2）在存储的数据量方面](#2%E5%9C%A8%E5%AD%98%E5%82%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E9%87%8F%E6%96%B9%E9%9D%A2)
    * [2、session 共享怎么做（分布式如何实现 session 共享）？（待写）](#2session-%E5%85%B1%E4%BA%AB%E6%80%8E%E4%B9%88%E5%81%9A%E5%88%86%E5%B8%83%E5%BC%8F%E5%A6%82%E4%BD%95%E5%AE%9E%E7%8E%B0-session-%E5%85%B1%E4%BA%AB%E5%BE%85%E5%86%99)
    * [3、在单点登录中，如果 cookie 被禁用了怎么办？](#3%E5%9C%A8%E5%8D%95%E7%82%B9%E7%99%BB%E5%BD%95%E4%B8%AD%E5%A6%82%E6%9E%9C-cookie-%E8%A2%AB%E7%A6%81%E7%94%A8%E4%BA%86%E6%80%8E%E4%B9%88%E5%8A%9E)
      * [单点登录的原理](#%E5%8D%95%E7%82%B9%E7%99%BB%E5%BD%95%E7%9A%84%E5%8E%9F%E7%90%86)
      * [被禁用的解决方法](#%E8%A2%AB%E7%A6%81%E7%94%A8%E7%9A%84%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95)
  * [四、jsp 技术](#%E5%9B%9Bjsp-%E6%8A%80%E6%9C%AF)
    * [1、什么是 jsp，什么是 servlet？jsp 和 servlet 有什么区别？](#1%E4%BB%80%E4%B9%88%E6%98%AF-jsp%E4%BB%80%E4%B9%88%E6%98%AF-servletjsp-%E5%92%8C-servlet-%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB)
      * [jsp 本质](#jsp-%E6%9C%AC%E8%B4%A8)
      * [Servlet](#servlet)
      * [区别](#%E5%8C%BA%E5%88%AB)
      * [jsp 运行机制](#jsp-%E8%BF%90%E8%A1%8C%E6%9C%BA%E5%88%B6)
    * [2、jsp 有哪些域对象和内置对象及他们的作用？](#2jsp-%E6%9C%89%E5%93%AA%E4%BA%9B%E5%9F%9F%E5%AF%B9%E8%B1%A1%E5%92%8C%E5%86%85%E7%BD%AE%E5%AF%B9%E8%B1%A1%E5%8F%8A%E4%BB%96%E4%BB%AC%E7%9A%84%E4%BD%9C%E7%94%A8)
      * [四大域对象](#%E5%9B%9B%E5%A4%A7%E5%9F%9F%E5%AF%B9%E8%B1%A1)
      * [（1）pageContext page 域](#1pagecontext-page-%E5%9F%9F)
      * [（2）request request 域](#2request-request-%E5%9F%9F)
      * [（3）session session 域](#3session-session-%E5%9F%9F)
      * [（4）application context 域](#4application-context-%E5%9F%9F)
      * [九大内置对象](#%E4%B9%9D%E5%A4%A7%E5%86%85%E7%BD%AE%E5%AF%B9%E8%B1%A1)
  * [五、XML 技术](#%E4%BA%94xml-%E6%8A%80%E6%9C%AF)
    * [1、什么是 xml，使用 xml 的优缺点，xml 的解析器有哪几种，分别有什么区别？](#1%E4%BB%80%E4%B9%88%E6%98%AF-xml%E4%BD%BF%E7%94%A8-xml-%E7%9A%84%E4%BC%98%E7%BC%BA%E7%82%B9xml-%E7%9A%84%E8%A7%A3%E6%9E%90%E5%99%A8%E6%9C%89%E5%93%AA%E5%87%A0%E7%A7%8D%E5%88%86%E5%88%AB%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB)
      * [xml 简介](#xml-%E7%AE%80%E4%BB%8B)
        * [优点](#%E4%BC%98%E7%82%B9)
        * [缺点](#%E7%BC%BA%E7%82%B9)
      * [Xml 常用解析器](#xml-%E5%B8%B8%E7%94%A8%E8%A7%A3%E6%9E%90%E5%99%A8)
        * [DOM 解析](#dom-%E8%A7%A3%E6%9E%90)
        * [SAX 解析](#sax-%E8%A7%A3%E6%9E%90)

# Java Web 基础

## 一、JDBC 技术

### 1、说下原生 jdbc 操作数据库流程？

#### 1）加载驱动

```java
Class.forName("com.mysql.jdbc.Driver");
```

#### 2）获取连接对象

```java
Connection conn=DriverManager.getConnection("jdbc:mysql://localhost:3306/student", "root", "root");
```

#### 3）根据 SQL 获取 sql 会话对象

两种方式 

Statement

```java
Statement st=conn.createStatement();
```

PreparedStatement

```java
PreparedStatement ps=conn.prepareStatement("select * from student where name=?");
```

4）执行 SQL 处理结果集，执行 SQL 前如果有参数值就设置参数值 setXXX()

Statement

```java
ResultSet rs=st.executeQuery("select * from student");
```

PreparedStatement

```java
ps.setString(1, "张三");
```

5）遍历结果集

```java
while(rs.next()) {
    result.append(rs.getInt("id")+"\t");
    result.append(rs.getString("name")+"\t");
    result.append(rs.getInt("age")+"\t");
    result.append(rs.getString("class")+"\t");
}
```

6）关闭

```java
if(rs != null) rs.close();
if(st != null) st.close();
//if(ps != null) ps.close();
if(conn != null) conn.close();
```

### 2、为什么要用 PreparedStatement？

1）PreparedStatement 接口继承 Statement，PreparedStatement 实例包含已编译的 SQL 语句，所以其执行速度要快于 Statement。

2） 作 为 Statement 的子类 ， PreparedStatement 继承了 Statement 的所有功能 。 

三种方法 execute、 executeQuery 和 executeUpdate 已被更改以使之不再需要参数。

3）在 JDBC 应用中,在任何时候都不要使用 Statement

原因如下：

 一、代码的可读性和可维护性.Statement 需要不断地拼接，而 PreparedStatement 不会。 

二、PreparedStatement 尽最大可能提高性能.DB 有缓存机制，相同的预编译语句再次被调用不会再次需要编译。 

三、最重要的一点是极大地提高了安全性.Statement 容易被 SQL 注入，而 PreparedStatementc 传入的内容不会和 sql 语句发生任何匹配关系。 

### 3、关系数据库中连接池的机制是什么？

#### 前提

为数据库连接建立一个缓冲池。

#### 1）从连接池获取或创建可用连接

#### 2）使用完毕之后

把连接返回给连接池

#### 3）在系统关闭前

断开所有连接并释放连接占用的系统资源

#### 4）能够处理无效连接

限制连接池中的连接总数不低于或者不超过某个限定值。

#### 几个概念

##### 最小连接数

连接池一直保持的数据连接。如果应用程序对数据库连接的使用量不大，将会有大量的数据库连接资源被浪费掉。

##### 最大连接数

连接池能申请的最大连接数。如果数据连接请求超过此数，后面的数据连接请求将被加入到等待队列中，这会影响之后的数据库操作。

##### 如果最小连接数与最大连接数相差太大

最先的连接请求将会获利，之后超过最小连接数量的连接请求等价于建立一个新的数据库连接。

不过，这些大于最小连接数的数据库连接在使用完不会马上被释放，它将被放到连接池中等待重复使用或是空闲超时后被释放。 

数据库池连接数量一直保持一个不少于最小连接数的数量，当数量不够时，数据库会创建一些连接，直到一个最大连接数，之后连接数据库就会等待。

## 二、http 协议

### 1、http 的长连接和短连接

HTTP 协议有 HTTP/1.0 版本和 HTTP/1.1 版本。

HTTP1.1 默认保持长连接（HTTP persistent connection，也翻译为持久连接），数据传输完成了保持 TCP 连接不断开（不发 RST 包、不四次握手），等待在同域名下继续用这个通道传输数据；相反就是短连接。

在 HTTP/1.0 中，默认使用的是短连接。

浏览器和服务器每进行一次 HTTP 操作，就建立一次连接，任务结束就中断连接。

从 HTTP/1.1 起，默认使用的是长连接，用以保持连接特性。

### 2、HTTP/1.1 与 HTTP/1.0 的区别

#### 1）可扩展性 

a) HTTP/1.1 在消息中增加版本号，用于兼容性判断。 

b) HTTP/1.1 增加了 OPTIONS 方法，它允许客户端获取一个服务器支持的方法列表。 

c) 为了与未来的协议规范兼容，HTTP/1.1 在请求消息中包含了 Upgrade 头域，通过该头域，客户端可以让服 务器知道它能够支持的其它备用通信协议，服务器可以据此进行协议切换，使用备用协议与客户端进行通信。

#### 2）缓存

在 HTTP/1.0 中，使用 Expire 头域来判断资源的 fresh 或 stale，并使用条件请求（conditional request）来判断资源是否仍有效。

HTTP/1.1 在 1.0 的基础上加入了一些 cache 的新特性，当缓存对象的 Age 超过 Expire 时变为 stale 对象，cache 不需要直接抛弃 stale 对象，而是与源服务器进行重新激活（revalidation）。

#### 3）带宽优化

##### HTTP/1.0 中，存在一些浪费带宽的现象

**例如**，客户端只是需要某个对象的一部分，而服务器却将整个对象送过来 了。

**例如**，客户端只需要显示一个文档的部分内容，又比如下载大文件时需要支持断点续传功能，而不是在发生断连后 不得不重新下载完整的包。 

##### HTTP/1.1 中在请求消息中引入了 range 头域

它允许只请求资源的某个部分。

在响应消息中 Content-Range 头 域声明了返回的这部分对象的偏移值和长度。

如果服务器相应地返回了对象所请求范围的内容，则响应码为 206 （Partial Content），它可以防止 Cache 将响应误以为是完整的一个对象。 

另外一种情况是请求消息中如果包含比 较大的实体内容，但不确定服务器是否能够接收该请求（如是否有权限）， 此时若贸然发出带实体的请求，如果被拒绝也会浪费带宽。 

##### HTTP/1.1 加入了一个新的状态码 100（Continue）。

客户端事先发送一个只带头域的请求，如果服务器因为权 限拒绝了请求，就回送响应码 401（Unauthorized）；

如果服务器接收此请求就回送响应码 100，客户端就可以继续 发送带实体的完整请求了。

注意，HTTP/1.0 的客户端不支持 100 响应码。但可以让客户端在请求消息中加入 Expect 头域，并将它的值设置为 100-continue。

##### 节省带宽资源的一个非常有效的做法就是压缩要传送的数据

Content-Encoding 是对消息进行端到端（end-toend）的编码，它可能是资源在服务器上保存的固有格式（如 jpeg 图片格式）；

在请求消息中加入 Accept-Encoding 头域，它可以告诉服务器客户端能够解码的编码方式。 

#### 4）长连接 

##### HTTP/1.0 规定浏览器与服务器只保持短暂的连接

浏览器的每次请求都需要与服务器建立一个 TCP 连接，服务 器完成请求处理后立即断开 TCP 连接，服务器不跟踪每个客户也不记录过去的请求。

此外，由于大多数网页的流量都比较小，一次 TCP 连接很少能通过 slow-start 区，不利于提高带宽利用率。 

##### HTTP 1.1 支持长连接（PersistentConnection）和请求的流水线（Pipelining）处理

在一个 TCP 连接上可以传 送多个 HTTP 请求和响应，减少了建立和关闭连接的消耗和延迟。

**例如**，一个包含有许多图像的网页文件的多个请求 和应答可以在一个连接中传输，但每个单独的网页文件的请求和应答仍然需要使用各自的连接。 

##### HTTP 1.1 还允许客户端不用等待上一次请求结果返回，就可以发出下一次请求

但服务器端必须按照接收到客户端请求的先后顺序依次回送响应结果，以保证客户端能够区分出每次请求的响应内容，这样也显著地减少了整个下载过程所需要的时间。

#### 5）消息传递 

##### HTTP 消息中可以包含任意长度的实体

通常它们使用 Content-Length 来给出消息结束标志。

但是，对于很多动 态产生的响应，只能通过缓冲完整的消息来判断消息的大小，但这样做会加大延迟。

如果不使用长连接，还可以通过连 接关闭的信号来判定一个消息的结束。

##### HTTP/1.1 中引入了 Chunkedtransfer-coding 来解决上面这个问题

发送方将消息分割成若干个任意大小的数据块，每个数据块在发送时都会附上块的长度，最后用一个零长度的块作为消息结束的标志。

这种方法允许发送方只缓冲消息的一个片段，避免缓冲整个消息带来的过载。 

##### 在 HTTP/1.0 中，有一个 Content-MD5 的头域

要计算这个头域需要发送方缓冲完整个消息后才能进行。

而 HTTP/1.1 中，采用 chunked 分块传递的消息在最后一个块（零长度）结束之后会再传递一个拖尾（trailer），它包 含一个或多个头域，这些头域是发送方在传递完所有块之后再计算出值的。

发送方会在消息中包含一个 Trailer 头域告 诉接收方这个拖尾的存在。

#### 6）Host 头域 

##### 在 HTTP1.0 中认为每台服务器都绑定一个唯一的 IP 地址

因此，请求消息中的 URL 并没有传递主机名（hostname）。

但随着虚拟主机技术的发展，在一台物理服务器上可以存在多个虚拟主机（Multi-homed Web Servers），并且它们 共享一个 IP 地址。 

##### HTTP1.1 的请求消息和响应消息都应支持 Host 头域，且请求消息中如果没有 Host 头域会报告一个错误（400 Bad Request）

此外，服务器应该接受以绝对路径标记的资源请求。

#### 7）错误提示 

##### HTTP/1.0 中只定义了 16 个状态响应码，对错误或警告的提示不够具体

HTTP/1.1 引入了一个 Warning 头域， 增加对错误或警告信息的描述。 

##### HTTP/1.1 中新增了 24 个状态响应码

**如** 409（Conflict）表示请求的资源与资源的当前状态发生冲突； 410（Gone）表示服务器上的某个资源被永久性的删除。

### 3、http 常见的状态码有哪些？

**200** **OK** 

//客户端请求成功 

**301** **Moved Permanently**

//（永久移除)，请求的 URL 已移走。

Response 中应该包含一个 Location URL, 说明资 源现在所处的位置 

**302** **found** 

//重定向 

**400** **Bad Request** 

//客户端请求有语法错误，不能被服务器所理解 

**401 Unauthorized** 

//请求未经授权，这个状态代码必须和 WWW-Authenticate 报头域一起使用 

**403 Forbidden** 

//服务器收到请求，但是拒绝提供服务 

**404 Not Found** 

//请求资源不存在，eg：输入了错误的 URL 

**500 Internal Server Error** 

//服务器发生不可预期的错误 

**503 Server Unavailable** 

//服务器当前不能处理客户端的请求，一段时间后可能恢复正常

### 4、GET 和 POST 的区别？

#### 1）请求数据位置

##### GET 请求的数据会附在 URL 之后

就是把数据放置在 HTTP 协议头中，以 ? 分割 URL 和传输数据，参数之间以 & 相连，如：login.action?name=zhagnsan&password=123456。

##### POST 把提交的数据则放置在是 HTTP 包的包体中。

#### 2）GET 方式提交的数据最多只能是 1024 字节，理论上 POST 没有限制，可传较大量的数据

其实这样说是**错误的**，不准确的： “GET 方式提交的数据最多只能是 1024 字节"，因为 GET 是通过 URL 提交数据，那么 GET 可提交的数据量就跟 URL 的长度有直接关系了。

而实际上，URL 不存在参数上限的问题，HTTP 协议规范没有对 URL 长度进行限制。

这个限制是特定的浏览器及服务器对它的限制。

IE 对 URL 长度的限制是 2083 字节(2K+35)。

对于其他浏览器，如 Netscape、 FireFox 等，理论上没有长度限制，其限制取决于操作系统的支持。

####  3）POST 的安全性要比 GET 的安全性高

注意：这里所说的安全性和上面 GET 提到的“安全”不是同个概念。 

上面“安全”的含义仅仅是不作数据修改，而这里安全的含义是真正的 Security 的含义

比如：通过 GET 提交数据， 用 户名和密码将明文出现在 URL 上，因为

（1）登录页面有可能被浏览器缓存

（2）其他人查看浏览器的历史纪录，那 么别人就可以拿到你的账号和密码了，除此之外，使用 GET 提交数据还可能会造成 Cross-site request forgery 攻击。

Get 是向服务器发索取数据的一种请求，而 Post 是向服务器提交数据的一种请求，在 FORM（表单）中，Method 默认为"GET"，实质上，GET 和 POST 只是发送机制不同，并不是一个取一个发！

参考原文： https://www.cnblogs.com/hyddd/archive/2009/03/31/1426026.html 

### 5、http 中重定向和请求转发的区别？

#### 本质区别

转发是服务器行为，重定向是客户端行为。

##### 重定向特点

两次请求，浏览器地址发生变化，可以访问 web 外的资源，传输数据会丢失。

##### 请求转发特点

一次请求，浏览器地址不变，访问的是自己本身的 web 资源，传输数据不会丢失。

## 三、Cookie 和 Session

### 1、Cookie 和 Session 的区别

#### Cookie 

是 web 服务器发送给浏览器的一块信息。

浏览器会在本地一个文件中给每个 web 服务器存储 cookie。 

以后浏览器再给特定的 web 服务器发送请求时，同时会发送所有为该服务器存储的 cookie。

#### Session

是存储在 web 服务器端的一块信息。

session 对象存储特定用户会话所需的属性及配置信息。

当用户在 应用程序的 Web 页之间跳转时，存储在 Session 对象中的变量将不会丢失，而是在整个用户会话中一直存在下去。

#### Cookie 和 Session 的不同点

##### 1）无论客户端做怎样的设置

session 都能够正常工作。当客户端禁用 cookie 时将无法使用 cookie。

##### 2）在存储的数据量方面

session 能够存储**任意的 java 对象**，cookie 只能存储 **String** 类型的对象。

### 2、session 共享怎么做（分布式如何实现 session 共享）？（待写）

session 复制 + 维护在客户端

### 3、在单点登录中，如果 cookie 被禁用了怎么办？

#### 单点登录的原理

后端生成一个 session ID，然后设置到 cookie，后面的所有请求浏览器都会带上 cookie， 然后服务端从 cookie 里获取 session ID，再查询到用户信息。

#### 被禁用的解决方法

保持登录的关键不是 cookie，而是通过 cookie 保存和传输的 session ID，其本质是能获取用户信息的数据。

除了 cookie，还通常使用 HTTP 请求头来传输。

但是这个请求头浏览器不会像 cookie 一样自动携带，需要手工处理。 

## 四、jsp 技术

### 1、什么是 jsp，什么是 servlet？jsp 和 servlet 有什么区别？

#### jsp 本质

就是一个 servlet，它是 servlet 的一种特殊形式，每个 jsp 页面都是一个 servlet 实例。

#### Servlet 

Java 提供用于开发 web 服务器应用程序的一个组件，运行在服务端，由 servlet 容器管理，用来生成动态内容。

一个 servlet 实例是实现了特殊接口 Servlet 的 Java 类，所有自定义的 servlet 均必须实现 Servlet 接 口。 

#### 区别

jsp 是 html 页面中内嵌的 java 代码，侧重页面显示；

servlet 是 html 代码和 java 代码分离，侧重逻辑控制，mvc 设计思想中 jsp 位于视图层，servlet 位于控制层。

#### jsp 运行机制

![052104163325510](C:\Users\13014\Desktop\052104163325510.gif)

jvm 只能识别 Java 类，并不能识别 jsp 代码。

1）web 容器收到以.jsp 为扩展名的 url 请求时

会将访问请求交给 tomcat 中 jsp 引擎处理

2）每个 jsp 页面第一次被访问时

jsp 引擎将 jsp 代码解释为一个 servlet 源程序

3）接着编译 servlet 源程序生成.class 文件

4）再由 web 容器 servlet 引擎去装载执行 servlet 程序，实现页面交互。 

### 2、jsp 有哪些域对象和内置对象及他们的作用？

#### 四大域对象

#### （1）pageContext page 域

指当前页面，在当前 jsp 页面有效，跳到其它页面失效 

#### （2）request request 域

指一次请求范围内有效，从 http 请求到服务器处理结束，返回响应的整个过程。 在这个过程中使用 forward（请求转发）方式跳转多个 jsp，在这些页面里你都可以使用这个变量 

#### （3）session session 域

指当前会话有效范围，浏览器从打开到关闭过程中，转发、重定向均可以使用 

#### （4）application context 域

指只能在同一个 web 中使用，服务器未关闭或者重启，数据就有效

#### 九大内置对象

|             | 生命周期                                                     | 作用域               | 使用情况                                                     |
| :---------- | :----------------------------------------------------------- | :------------------- | :----------------------------------------------------------- |
| Request     | 一次请求                                                     | 只在 Jsp 页面内 有效 | 用于接受通过 HTTP 协议传送到服务器 的数据（包括头信息、系统信息、请 求方式以及请求参数等）。 |
| Reponse     | 一次响应                                                     | 只在 Jsp 页面内 有效 | 有效 表示服务器端对客户端的回应。主要 用于设置头信息、跳转、Cookie 等 |
| Session     | 从存入数据开始，默认闲置 30 分钟后失 效                      | 会话内有效           | 用于存储特定的用户会话所需的信息                             |
| Out         |                                                              |                      | 用于在 Web 浏览器内输出信息，并且 管理应用服务器上的输出缓冲区 |
| PageContext |                                                              |                      | 用于存取其他隐含对象，如 request、 reponse、session、application 等对 象。（实际上，pageContext 对象提供 了对 JSP 页面所有的对象及命名空间的 访问。 |
| Page        |                                                              |                      | page 对象代表 JSP 本身（对应 this）， 只有在 JSP 页面内才是合法的 |
| Exception   |                                                              |                      | 显示异常信息，必须在 page 指令中设 定< %@ page isErrorPage="true" %>才能 使用，在一般的 JSP 页面中使用该对象 将无法编译 JSP 文件 |
| Application | 服务器启动发送第一个请求时就产生了 Application 对象，直到服务器关闭。 |                      | 用于存储和访问来自任何页面的变量 所有的用户分享一个 Application 对象 |
| Config      |                                                              |                      | 取得服务器的配置信息                                         |



## 五、XML 技术

### 1、什么是 xml，使用 xml 的优缺点，xml 的解析器有哪几种，分别有什么区别？

#### xml 简介

xml 是一种可扩展性标记语言，支持自定义标签（使用前必须预定义）使用 DTD 和 XML Schema 标准化 XML 结构。

##### 优点

用于配置文件，格式统一，符合标准；用于在互不兼容的系统间交互数据，共享数据方便； 

##### 缺点

xml 文件格式复杂，数据传输占流量，服务端和客户端解析 xml 文件占用大量资源且不易维护 

#### Xml 常用解析器

两种分别是：DOM 和 SAX; 

主要区别在于它们解析 xml 文档的方式不同。

##### DOM 解析

xml 文档以 DOM 树形结构加载入内存。

##### SAX 解析

采用的是事件模型。