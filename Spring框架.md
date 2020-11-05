* [框架](#%E6%A1%86%E6%9E%B6)
  * [一、SpringMVC](#%E4%B8%80springmvc)
    * [搭建springmvc](#%E6%90%AD%E5%BB%BAspringmvc)
      * [1）引入依赖](#1%E5%BC%95%E5%85%A5%E4%BE%9D%E8%B5%96)
      * [2）编写application\.xml](#2%E7%BC%96%E5%86%99applicationxml)
      * [3）编写springmvc\.xml](#3%E7%BC%96%E5%86%99springmvcxml)
    * [1、SpringMVC的工作原理](#1springmvc%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86)
    * [2、SpringMVC常用注解都有哪些](#2springmvc%E5%B8%B8%E7%94%A8%E6%B3%A8%E8%A7%A3%E9%83%BD%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [3、如何开启注解处理器和适配器](#3%E5%A6%82%E4%BD%95%E5%BC%80%E5%90%AF%E6%B3%A8%E8%A7%A3%E5%A4%84%E7%90%86%E5%99%A8%E5%92%8C%E9%80%82%E9%85%8D%E5%99%A8)
    * [4、如何解决 get 和 post 乱码问题](#4%E5%A6%82%E4%BD%95%E8%A7%A3%E5%86%B3-get-%E5%92%8C-post-%E4%B9%B1%E7%A0%81%E9%97%AE%E9%A2%98)
  * [二、Spring](#%E4%BA%8Cspring)
    * [1、对Spring的理解](#1%E5%AF%B9spring%E7%9A%84%E7%90%86%E8%A7%A3)
    * [2、Spring 中的设计模式](#2spring-%E4%B8%AD%E7%9A%84%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F)
      * [1）单例模式](#1%E5%8D%95%E4%BE%8B%E6%A8%A1%E5%BC%8F)
      * [2）模板方式模式](#2%E6%A8%A1%E6%9D%BF%E6%96%B9%E5%BC%8F%E6%A8%A1%E5%BC%8F)
      * [3）前端控制器模式](#3%E5%89%8D%E7%AB%AF%E6%8E%A7%E5%88%B6%E5%99%A8%E6%A8%A1%E5%BC%8F)
      * [4）视图模式](#4%E8%A7%86%E5%9B%BE%E6%A8%A1%E5%BC%8F)
      * [5）包装器模式](#5%E5%8C%85%E8%A3%85%E5%99%A8%E6%A8%A1%E5%BC%8F)
      * [6）工厂模式](#6%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F)
        * [简单工厂模式](#%E7%AE%80%E5%8D%95%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F)
        * [工厂方法模式](#%E5%B7%A5%E5%8E%82%E6%96%B9%E6%B3%95%E6%A8%A1%E5%BC%8F)
      * [7）代理模式](#7%E4%BB%A3%E7%90%86%E6%A8%A1%E5%BC%8F)
      * [8）适配器模式](#8%E9%80%82%E9%85%8D%E5%99%A8%E6%A8%A1%E5%BC%8F)
    * [3、Spring 的常用注解](#3spring-%E7%9A%84%E5%B8%B8%E7%94%A8%E6%B3%A8%E8%A7%A3)
      * [使用bean](#%E4%BD%BF%E7%94%A8bean)
        * [@Autowired](#autowired)
        * [@Resource（属于J2EE）](#resource%E5%B1%9E%E4%BA%8Ej2ee)
      * [注册bean](#%E6%B3%A8%E5%86%8Cbean)
        * [@Component](#component)
        * [@Repository](#repository)
        * [@Controller](#controller)
        * [@Service](#service)
        * [@Configuration](#configuration)
        * [@WebListener](#weblistener)
    * [4、Spring bean 的生命周期](#4spring-bean-%E7%9A%84%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F)
      * [1、bean 定义](#1bean-%E5%AE%9A%E4%B9%89)
      * [2、bean 初始化（两种方法）](#2bean-%E5%88%9D%E5%A7%8B%E5%8C%96%E4%B8%A4%E7%A7%8D%E6%96%B9%E6%B3%95)
      * [3、bean 调用](#3bean-%E8%B0%83%E7%94%A8)
      * [4、bean 销毁（两种方式）](#4bean-%E9%94%80%E6%AF%81%E4%B8%A4%E7%A7%8D%E6%96%B9%E5%BC%8F)
    * [5、Spring 核心容器](#5spring-%E6%A0%B8%E5%BF%83%E5%AE%B9%E5%99%A8)
    * [6、Spring 能帮我们做什么](#6spring-%E8%83%BD%E5%B8%AE%E6%88%91%E4%BB%AC%E5%81%9A%E4%BB%80%E4%B9%88)
    * [7、Spring 的事务](#7spring-%E7%9A%84%E4%BA%8B%E5%8A%A1)
      * [1）Spring 事务传播机制](#1spring-%E4%BA%8B%E5%8A%A1%E4%BC%A0%E6%92%AD%E6%9C%BA%E5%88%B6)
        * [事务的特性](#%E4%BA%8B%E5%8A%A1%E7%9A%84%E7%89%B9%E6%80%A7)
          * [原子性](#%E5%8E%9F%E5%AD%90%E6%80%A7)
          * [一致性](#%E4%B8%80%E8%87%B4%E6%80%A7)
          * [隔离性](#%E9%9A%94%E7%A6%BB%E6%80%A7)
          * [持久性](#%E6%8C%81%E4%B9%85%E6%80%A7)
        * [Spring 事务的配置方式](#spring-%E4%BA%8B%E5%8A%A1%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F)
          * [1、编程式事务管理](#1%E7%BC%96%E7%A8%8B%E5%BC%8F%E4%BA%8B%E5%8A%A1%E7%AE%A1%E7%90%86)
          * [2、声明式事务管理](#2%E5%A3%B0%E6%98%8E%E5%BC%8F%E4%BA%8B%E5%8A%A1%E7%AE%A1%E7%90%86)
          * [3、事务的传播机制](#3%E4%BA%8B%E5%8A%A1%E7%9A%84%E4%BC%A0%E6%92%AD%E6%9C%BA%E5%88%B6)
      * [2）事务的隔离级别](#2%E4%BA%8B%E5%8A%A1%E7%9A%84%E9%9A%94%E7%A6%BB%E7%BA%A7%E5%88%AB)
        * [1、脏读（Dirty read）](#1%E8%84%8F%E8%AF%BBdirty-read)
        * [2、不可重复读（Nonrepeatable read）](#2%E4%B8%8D%E5%8F%AF%E9%87%8D%E5%A4%8D%E8%AF%BBnonrepeatable-read)
        * [3、幻读（Phantom reads）](#3%E5%B9%BB%E8%AF%BBphantom-reads)
      * [3）只读](#3%E5%8F%AA%E8%AF%BB)
      * [4）事务超时](#4%E4%BA%8B%E5%8A%A1%E8%B6%85%E6%97%B6)
      * [5）回滚规则](#5%E5%9B%9E%E6%BB%9A%E8%A7%84%E5%88%99)
      * [6）Spring声明式事务配置参考](#6spring%E5%A3%B0%E6%98%8E%E5%BC%8F%E4%BA%8B%E5%8A%A1%E9%85%8D%E7%BD%AE%E5%8F%82%E8%80%83)
    * [8、BeanFactory 常用实现类有哪些](#8beanfactory-%E5%B8%B8%E7%94%A8%E5%AE%9E%E7%8E%B0%E7%B1%BB%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [9、解释 Spring JDBC、Spring DAO 和 Spring ORM](#9%E8%A7%A3%E9%87%8A-spring-jdbcspring-dao-%E5%92%8C-spring-orm)
      * [1）Spring JDBC](#1spring-jdbc)
      * [2）Spring DAO](#2spring-dao)
      * [3）Spring ORM](#3spring-orm)
    * [10、简单介绍一下 SpringWEB 模块](#10%E7%AE%80%E5%8D%95%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8B-springweb-%E6%A8%A1%E5%9D%97)
    * [11、Spring 配置文件有什么用](#11spring-%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E6%9C%89%E4%BB%80%E4%B9%88%E7%94%A8)
    * [12、什么是 Spring IOC 容器](#12%E4%BB%80%E4%B9%88%E6%98%AF-spring-ioc-%E5%AE%B9%E5%99%A8)
    * [13、IOC 的优点是什么](#13ioc-%E7%9A%84%E4%BC%98%E7%82%B9%E6%98%AF%E4%BB%80%E4%B9%88)
    * [14、ApplicationContext 的实现类有哪些](#14applicationcontext-%E7%9A%84%E5%AE%9E%E7%8E%B0%E7%B1%BB%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [15、BeanFactory 与 ApplicationContext 有什么区别](#15beanfactory-%E4%B8%8E-applicationcontext-%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB)
      * [1）BeanFactory](#1beanfactory)
      * [2）ApplicationContext](#2applicationcontext)
    * [16、什么是 Spring 的依赖注入](#16%E4%BB%80%E4%B9%88%E6%98%AF-spring-%E7%9A%84%E4%BE%9D%E8%B5%96%E6%B3%A8%E5%85%A5)
    * [17、有哪些不同类型的 IOC（依赖注入）方式？](#17%E6%9C%89%E5%93%AA%E4%BA%9B%E4%B8%8D%E5%90%8C%E7%B1%BB%E5%9E%8B%E7%9A%84-ioc%E4%BE%9D%E8%B5%96%E6%B3%A8%E5%85%A5%E6%96%B9%E5%BC%8F)
      * [1、Set 注入](#1set-%E6%B3%A8%E5%85%A5)
      * [2、构造器注入](#2%E6%9E%84%E9%80%A0%E5%99%A8%E6%B3%A8%E5%85%A5)
      * [3、静态工厂方法注入](#3%E9%9D%99%E6%80%81%E5%B7%A5%E5%8E%82%E6%96%B9%E6%B3%95%E6%B3%A8%E5%85%A5)
      * [4、实力工厂方法注入](#4%E5%AE%9E%E5%8A%9B%E5%B7%A5%E5%8E%82%E6%96%B9%E6%B3%95%E6%B3%A8%E5%85%A5)
    * [18、什么是 Spring beans](#18%E4%BB%80%E4%B9%88%E6%98%AF-spring-beans)
    * [19、一个 Spring Beans 的定义需要包含什么？](#19%E4%B8%80%E4%B8%AA-spring-beans-%E7%9A%84%E5%AE%9A%E4%B9%89%E9%9C%80%E8%A6%81%E5%8C%85%E5%90%AB%E4%BB%80%E4%B9%88)
    * [20、怎样定义类的作用域?](#20%E6%80%8E%E6%A0%B7%E5%AE%9A%E4%B9%89%E7%B1%BB%E7%9A%84%E4%BD%9C%E7%94%A8%E5%9F%9F)
    * [21、Spring 支持的几种 bean 的作用域](#21spring-%E6%94%AF%E6%8C%81%E7%9A%84%E5%87%A0%E7%A7%8D-bean-%E7%9A%84%E4%BD%9C%E7%94%A8%E5%9F%9F)
      * [1）singleton](#1singleton)
      * [2）prototype](#2prototype)
      * [3）request](#3request)
      * [4）session](#4session)
      * [5）global\-session](#5global-session)
    * [22、 Spring 框架中的单例 bean 是线程安全的吗?](#22-spring-%E6%A1%86%E6%9E%B6%E4%B8%AD%E7%9A%84%E5%8D%95%E4%BE%8B-bean-%E6%98%AF%E7%BA%BF%E7%A8%8B%E5%AE%89%E5%85%A8%E7%9A%84%E5%90%97)
    * [23、什么是 Spring 的内部 bean？](#23%E4%BB%80%E4%B9%88%E6%98%AF-spring-%E7%9A%84%E5%86%85%E9%83%A8-bean)
    * [24、在 Spring 中如何注入一个 java 集合？](#24%E5%9C%A8-spring-%E4%B8%AD%E5%A6%82%E4%BD%95%E6%B3%A8%E5%85%A5%E4%B8%80%E4%B8%AA-java-%E9%9B%86%E5%90%88)
    * [25、什么是 bean 的自动装配？](#25%E4%BB%80%E4%B9%88%E6%98%AF-bean-%E7%9A%84%E8%87%AA%E5%8A%A8%E8%A3%85%E9%85%8D)
    * [26、解释不同方式的自动装配](#26%E8%A7%A3%E9%87%8A%E4%B8%8D%E5%90%8C%E6%96%B9%E5%BC%8F%E7%9A%84%E8%87%AA%E5%8A%A8%E8%A3%85%E9%85%8D)
      * [1）no](#1no)
      * [2）byName](#2byname)
      * [3）byType](#3bytype)
      * [4）constructor](#4constructor)
      * [5）autodetect](#5autodetect)
    * [27、什么是基于 java 的 Spring 注解配置？给一些注解例子](#27%E4%BB%80%E4%B9%88%E6%98%AF%E5%9F%BA%E4%BA%8E-java-%E7%9A%84-spring-%E6%B3%A8%E8%A7%A3%E9%85%8D%E7%BD%AE%E7%BB%99%E4%B8%80%E4%BA%9B%E6%B3%A8%E8%A7%A3%E4%BE%8B%E5%AD%90)
    * [28、什么是基于注解的容器配置？](#28%E4%BB%80%E4%B9%88%E6%98%AF%E5%9F%BA%E4%BA%8E%E6%B3%A8%E8%A7%A3%E7%9A%84%E5%AE%B9%E5%99%A8%E9%85%8D%E7%BD%AE)
    * [29、怎样开启注解装配](#29%E6%80%8E%E6%A0%B7%E5%BC%80%E5%90%AF%E6%B3%A8%E8%A7%A3%E8%A3%85%E9%85%8D)
    * [30、在 Spring 框架中如何更有效地使用 JDBC](#30%E5%9C%A8-spring-%E6%A1%86%E6%9E%B6%E4%B8%AD%E5%A6%82%E4%BD%95%E6%9B%B4%E6%9C%89%E6%95%88%E5%9C%B0%E4%BD%BF%E7%94%A8-jdbc)
    * [31、使用 Spring 通过什么方式访问 Hibernate？](#31%E4%BD%BF%E7%94%A8-spring-%E9%80%9A%E8%BF%87%E4%BB%80%E4%B9%88%E6%96%B9%E5%BC%8F%E8%AE%BF%E9%97%AE-hibernate)
    * [32、Spring 支持的 ORM 框架有哪些？](#32spring-%E6%94%AF%E6%8C%81%E7%9A%84-orm-%E6%A1%86%E6%9E%B6%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [33、简单解释一下 spring 的 AOP](#33%E7%AE%80%E5%8D%95%E8%A7%A3%E9%87%8A%E4%B8%80%E4%B8%8B-spring-%E7%9A%84-aop)
    * [34、在 Spring AOP 中，关注点和横切关注的区别是什么？](#34%E5%9C%A8-spring-aop-%E4%B8%AD%E5%85%B3%E6%B3%A8%E7%82%B9%E5%92%8C%E6%A8%AA%E5%88%87%E5%85%B3%E6%B3%A8%E7%9A%84%E5%8C%BA%E5%88%AB%E6%98%AF%E4%BB%80%E4%B9%88)
    * [35、什么是连接点？](#35%E4%BB%80%E4%B9%88%E6%98%AF%E8%BF%9E%E6%8E%A5%E7%82%B9)
    * [36、Spring 的通知是什么？有哪几种类型？](#36spring-%E7%9A%84%E9%80%9A%E7%9F%A5%E6%98%AF%E4%BB%80%E4%B9%88%E6%9C%89%E5%93%AA%E5%87%A0%E7%A7%8D%E7%B1%BB%E5%9E%8B)
      * [1）before](#1before)
      * [2）after](#2after)
      * [3）after\-returning](#3after-returning)
      * [4）after\-throwing](#4after-throwing)
      * [5）around](#5around)
    * [37、什么是切点？](#37%E4%BB%80%E4%B9%88%E6%98%AF%E5%88%87%E7%82%B9)
    * [38、什么是目标对象?](#38%E4%BB%80%E4%B9%88%E6%98%AF%E7%9B%AE%E6%A0%87%E5%AF%B9%E8%B1%A1)
    * [39、什么是代理?](#39%E4%BB%80%E4%B9%88%E6%98%AF%E4%BB%A3%E7%90%86)
    * [40、什么是织入？什么是织入应用的不同点？](#40%E4%BB%80%E4%B9%88%E6%98%AF%E7%BB%87%E5%85%A5%E4%BB%80%E4%B9%88%E6%98%AF%E7%BB%87%E5%85%A5%E5%BA%94%E7%94%A8%E7%9A%84%E4%B8%8D%E5%90%8C%E7%82%B9)

# 框架

依赖豪华版（spring）

```xml
  <properties>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
    <spring.version>5.0.0.RELEASE</spring.version>
    <commons-logging.version>1.2</commons-logging.version>
  </properties>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
    <!-- https://mvnrepository.com/artifact/commons-logging/commons-logging -->
    <dependency>
      <groupId>commons-logging</groupId>
      <artifactId>commons-logging</artifactId>
      <version>1.1.1</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/log4j/log4j -->
    <dependency>
      <groupId>log4j</groupId>
      <artifactId>log4j</artifactId>
      <version>1.2.17</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-core -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-core</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-context -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-beans -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-beans</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
    <!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
    <dependency>
      <groupId>mysql</groupId>
      <artifactId>mysql-connector-java</artifactId>
      <version>8.0.21</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/aopalliance/aopalliance -->
    <dependency>
      <groupId>aopalliance</groupId>
      <artifactId>aopalliance</artifactId>
      <version>1.0</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-aop -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-aop</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.aspectj/aspectjweaver -->
    <dependency>
      <groupId>org.aspectj</groupId>
      <artifactId>aspectjweaver</artifactId>
      <version>1.8.1</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-aspects -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-aspects</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-jdbc -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-jdbc</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-test</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!--springmvc  -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-web</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-webmvc</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
    <dependency>
      <groupId>mysql</groupId>
      <artifactId>mysql-connector-java</artifactId>
      <version>8.0.18</version>
    </dependency>
    <!-- MyBatis -->
    <dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis</artifactId>
      <version>3.4.6</version>
    </dependency>
    <!-- mybatis-spring -->
    <dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis-spring</artifactId>
      <version>1.3.0</version>
    </dependency>
    <!-- spring-jdbc -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-jdbc</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!-- dbcp -->
    <dependency>
      <groupId>org.apache.commons</groupId>
      <artifactId>commons-dbcp2</artifactId>
      <version>2.1.1</version>
    </dependency>
    <dependency>
      <groupId>org.apache.commons</groupId>
      <artifactId>commons-pool2</artifactId>
      <version>2.4.2</version>
    </dependency>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
```



## 一、SpringMVC

### 搭建springmvc

#### 1）引入依赖

```java
<properties>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
    <spring.version>5.0.0.RELEASE</spring.version>
    <commons-logging.version>1.2</commons-logging.version>
  </properties>
  <dependencies>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-core</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-beans</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <!--springmvc  -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-web</artifactId>
      <version>${spring.version}</version>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-webmvc</artifactId>
      <version>${spring.version}</version>
    </dependency>
  </dependencies>
```

#### 2）编写application.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
                            http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.3.xsd">
    <context:annotation-config></context:annotation-config>
</beans>
```

#### 3）编写springmvc.xml

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:mvc="http://www.springframework.org/schema/mvc"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.3.xsd
		http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc-4.3.xsd">
    <context:component-scan base-package="com.lhq.controller"></context:component-scan>
    <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <property name="prefix" value="/WEB-INF/jsp/"></property>
        <property name="suffix" value=".jsp"></property>
    </bean>
    <mvc:annotation-driven></mvc:annotation-driven>
    <mvc:resources mapping="/js/**" location="/js/"></mvc:resources>
</beans>
```

配置web.xml

```java
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://java.sun.com/xml/ns/javaee" xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" version="2.5">
  <display-name>Archetype Created Web Application</display-name>
  <welcome-file-list>
    <welcome-file>index.jsp</welcome-file>
  </welcome-file-list>
  <context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>classpath:application.xml</param-value>
  </context-param>
  <listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
  </listener>
  <filter>
    <filter-name>encoding</filter-name>
    <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
    <init-param>
      <param-name>encoding</param-name>
      <param-value>UTF-8</param-value>
    </init-param>
  </filter>
  <filter-mapping>
    <filter-name>encoding</filter-name>
    <!--    此处应为"/*"-->
    <url-pattern>*</url-pattern>
  </filter-mapping>
  <servlet>
    <servlet-name>springmvc</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <init-param>
      <param-name>contextConfigLocation</param-name>
      <param-value>classpath:springmvc.xml</param-value>
    </init-param>
  </servlet>
  <servlet-mapping>
    <servlet-name>springmvc</servlet-name>
    <url-pattern>/</url-pattern>
  </servlet-mapping>
</web-app>
```

### 1、SpringMVC的工作原理

用户向服务器发送请求，请求被前端控制器DispatcherServlet捕获

DispatcherServlet对URL进行解析，根据URL调用HandlerMapping将请求映射到处理器HandlerExcutionChain

DispatcherServlet根据获得的Handler选择一个合适的HandlerAdapter适配器处理

HandlerAdapter返回一个ModelAndView逻辑视图给DisptcherServlet

DisptcherServlet将ModelAndView交给ViewResolver进行解析处理返回一个真正的视图

### 2、SpringMVC常用注解都有哪些

@RequestMapping 用于请求 url 映射

@RequestBody 注解实现接收 http 请求的 json 数据，将 json 数据转换为 java 对象

@ResponseBody 将Controller 方法返回对象转化为 json 响应给用户

### 3、如何开启注解处理器和适配器

在 springmvc.xml 中通过开启

```xml
<mvc:annotation-driven/>
```

来实现注解处理器和适配器的开启

### 4、如何解决 get 和 post 乱码问题

post：

在 web.xml 里面配置一个CharacterEncodingFilter 过滤器。设置编码格式为 utf-8

get：

修改 tomcat 配置文件添加编码和工程编码一致。

对参数重新编码

```java
String parm = new String(req.getParameter("parm").getBytes("前端编码格式"),"utf-8");
```

## 二、Spring

### 1、对Spring的理解

Spring是一个IOC和AOP框架。

核心是：

控制反转（IOC）：在spring开发中，spring容器使用工厂模式为我们创建了所需要的对象，不需要我们自己创建，直接调用spring提供的对象就行。

依赖注入（DI）：spring 通过 set 方法或者带参数的构造方法为我们创建所需对象时将其属性自动设置所需要的值。

面向切面编程（AOP）：面向对象将事务纵向成一个个的对象。在面向切面编程中，将一个个对象某些类似方面横向抽成一个切面，对这个切面进行一些权限控制、事务管理，记录日志等公用操作处理的过程就是面向切面编程。AOP底层是动态代理，如果是接口采用 JDK 动态代理，如果是类采用 CGLIB 方式实现动态代理。

### 2、Spring 中的设计模式

#### 1）单例模式

在 spring 的配置文件中的 bean 默认为单例模式。

#### 2）模板方式模式

用来解决代码重复的问题

如：RestTemplate、JmsTemplate、JpaTemplate。

#### 3）前端控制器模式

使用 DispatcherServlet 来对请求进行分发。

#### 4）视图模式

spring 提供了一系列 JSP 标签，将分散的代码整合在视图中。

#### 5）包装器模式

spring中用到的包装器模式在类名上有两种表现：一种是类名中含有Wrapper，另一种是类名中含有Decorator。基本上都是动态地给一个对象添加一些额外的职责。

#### 6）工厂模式

##### 简单工厂模式

又叫做静态工厂方法(StaticFactory Method)模式　

简单工厂模式的实质是由一个工厂类根据传入的参数，动态决定应该创建哪一个产品类。spring中的BeanFactory就是简单工厂模式的体现，根据传入一个唯一的标识来获得bean对象，但是否是在传入参数后创建还是传入参数前创建这个要根据具体情况来定。

##### 工厂方法模式

通常由应用程序直接使用new创建新的对象，为了将对象的创建和使用相分离，采用工厂模式,即应用程序将对象的创建及初始化职责交给工厂对象。

一般情况下,应用程序有自己的工厂对象来创建bean.如果将应用程序自己的工厂对象交给Spring管理,那么Spring管理的就不是普通的bean,而是工厂Bean。

#### 7）代理模式

spring 中两种代理方式，若目标对象实现了若干接口，spring 使用 jdk 的java.lang.reflect.Proxy 类代理。若目标兑现没有实现任何接口，spring 使用 CGLIB 库生成目标类的子类。

#### 8）适配器模式

在Spring的Aop中，使用的Advice(通知)来增强被代理类的功能。Spring实现这一AOP功能的原理就使用代理模式对类进行方法级别的切面增强，即，生成被代理类的代理类， 并在代理类的方法前，设置拦截器，通过执行拦截器重的内容增强了代理方法的功能，实现的面向切面编程。

### 3、Spring 的常用注解

开启注解

```xml
<context:annotation-config/>
```

常用注解

#### 使用bean

##### @Autowired

@Autowired(required=false) 

它可以对类成员变量、方法及构造函数进行标注，完成自动装配的工作。 通过 @Autowired的使用来消除 set ，get方法。

如果我们想使用名称装配可以结合@Qualifier注解进行使用

required属性

required属性值可以为true（ 默认值）和false。如果为true的话，没有匹配的类则抛出异常；如果为false，则表示不是强制必须能够找到相应的类，无论是否注入成功，都不会抛错。

##### @Resource（属于J2EE）

```java
@Resource(name="baseDao")
private BaseDao baseDao;
```

#### 注册bean

##### @Component

1、把pojo实例化到spring容器中，相当于配置文件中的

```xml
<bean id="" class=""/>
```

2、引入component扫描组件

```xml
<context:component-scan base-package=""/>
```

##### @Repository

1、@Repository跟@Service，@Component，@Controller这4种注解是没什么本质区别,都是声明作用,取不同的名字只是为了更好区分各自的功能。

2、因为接口没办法在spring.xml中用bean的方式来配置实现类吧(接口配不了),所以只能用注解或者mybatis.xml中扫描bean的方式来生成实现类。

3、@repository是用来注解接口

4、有时候我们不用@repository来注解接口,我们照样可以注入到这个接口的实现类，原因是我们在xml文件中扫描了其所在的包，并注册到spring容器中。

##### @Controller

1、@Controller 和 @RestController 都是标识一个类为控制器（类似 servlet）。只不过  @RestController 标识当前类方法返回值默认转为json串。

2、@Controller 标识类的方法上注解 @ResponseBody 表示返回 json 数据，也就是将返回值转为 json 字符串。

##### @Service

相当于在xml配置

```xml
<bean id="" class="" scope="prototype"></bean>
```

##### @Configuration

@Configuration 的注解类表示这个类可以使用 SpringIoC 容器作为 bean 定义的来源。

##### @WebListener

注册监听器注解。

### 4、Spring bean 的生命周期

#### 1、bean 定义

在配置文件中使用 <bean></bean> 来进行定义。

#### 2、bean 初始化（两种方法）

1）在配置文件使用 init-method 属性来完成。

2）实现 org.springframwork.beans.factory.InitializingBean 接口。

#### 3、bean 调用

#### 4、bean 销毁（两种方式）

1.使用配置文件指定的 destroy-method 属性。 

2.实现 org.springframwork.bean.factory.DisposeableBean 接口。



### 5、Spring 核心容器

包括 Core、Beans、Context、EL 模块。

### 6、Spring 能帮我们做什么

1、根据配置文件创建及组装对象之间的依赖关系。

2、面向切面编程能帮我们无耦合的实现日志记录，性能统计，安全控制。

3、能非常简单的帮助我们管理数据库事务，我们只需要获取连接，执行 sql ，其他事务相关的都交给 Spring 来管理。

4、能与第三方数据库访问框架无缝集成，而且自己也提供了一套 JDBC 访问模板，来方便数据库访问。

5、能与第三方 Web 框架无缝集成，而且自己也提供了一套 SpringMVC 框架，来方便 web 层搭建。

6、能方便的与 Java EE（如Java Mail、任务调度）整合，与更多技术整合（如缓存框架）。

### 7、Spring 的事务

#### 1）Spring 事务传播机制

##### 事务的特性

###### 原子性

保证动作要么全部完成，要么完全不起作用

###### 一致性

一旦事务完成（不管成功还是失败），系统必须保证它所建模的业务处于一致的状态，而不是部分失败。在现实中的数据不应被破坏。

###### 隔离性

许多事务会同时处理相同的数据，因此每个事务都应该与其他事务隔离开来，防止数据损坏。

###### 持久性

一旦事务完成，无论发生什么系统错误，它的结果都不应该受影响，这样就能从任何系统崩溃中恢复过来。通常情况下，事务的结果被写道持久化存储器中。

##### Spring 事务的配置方式

###### 1、编程式事务管理

编程性事务管理是侵入性事务管理，使用 TransactionTemplate 或者直接使用 PlatformTransactionManager，对于编程式事务管理，Spring 推荐使用 TransactionTemplate。

###### 2、声明式事务管理

声明式事务管理建立在 AOP 上，本质是对方法前后进行拦截，然后再目标方法开始之前创建或者加入一个事务，执行完目标方法之后根据执行的情况提交或者回滚。

编程式事务每次实现都要单独实现，但业务量大功能复杂时，使用编程式事务无疑是痛苦的，而声明式事务不同，声明式事务属于无侵入式，不会影响业务逻辑的实现，只需要在配置文件中做相关的事务规则声明或者通过注解的方式，便可以将事务规则应用到业务逻辑中。
显然声明式事务管理要优于编程式事务管理，这正是Spring倡导的非侵入式的编程方式。唯一不足的地方就是声明式事务管理的粒度是方法级别，而编程式事务管理是可以到代码块的，但是可以通过提取方法的方式完成声明式事务管理的配置。

###### 3、事务的传播机制

事务的传播性一般用在事务嵌套的场景，比如一个事务方法里面调用了另外一个事务方法，那么两个方法是各自作为独立的方法提交还是内层的事务合并到外层的事务一起提交，这就是需要事务传播机制的配置来确定怎么样执行。
常用的事务传播机制如下：

- PROPAGATION_REQUIRED
  Spring默认的传播机制，能满足绝大部分业务需求，如果外层有事务，则当前事务加入到外层事务，一块提交，一块回滚。如果外层没有事务，新建一个事务执行
- PROPAGATION_REQUES_NEW
  该事务传播机制是每次都会新开启一个事务，同时把外层事务挂起，当当前事务执行完毕，恢复上层事务的执行。如果外层没有事务，执行当前新开启的事务即可
- PROPAGATION_SUPPORT
  如果外层有事务，则加入外层事务，如果外层没有事务，则直接使用非事务方式执行。完全依赖外层的事务
- PROPAGATION_NOT_SUPPORT
  该传播机制不支持事务，如果外层存在事务则挂起，执行完当前代码，则恢复外层事务，无论是否异常都不会回滚当前的代码
- PROPAGATION_NEVER
  该传播机制不支持外层事务，即如果外层有事务就抛出异常
- PROPAGATION_MANDATORY
  与NEVER相反，如果外层没有事务，则抛出异常
- PROPAGATION_NESTED
  该传播机制的特点是可以保存状态保存点，当前事务回滚到某一个点，从而避免所有的嵌套事务都回滚，即各自回滚各自的，如果子事务没有把异常吃掉，基本还是会引起全部回滚的。

**传播规则回答了这样一个问题：一个新的事务应该被启动还是被挂起，或者是一个方法是否应该在事务性上下文中运行。**

#### 2）事务的隔离级别

事务的隔离级别定义一个事务可能受其他并发务活动活动影响的程度，可以把事务的隔离级别想象为这个事务对于事物处理数据的自私程度。

在一个典型的应用程序中，多个事务同时运行，经常会为了完成他们的工作而操作同一个数据。并发虽然是必需的，但是会导致以下问题：

##### 1、脏读（Dirty read）

脏读发生在一个事务读取了被另一个事务改写但尚未提交的数据时。如果这些改变在稍后被回滚了，那么第一个事务读取的数据就会是无效的。

##### 2、不可重复读（Nonrepeatable read）

不可重复读发生在一个事务执行相同的查询两次或两次以上，但每次查询结果都不相同时。这通常是由于另一个并发事务在两次查询之间更新了数据。

**不可重复读重点在修改**。

##### 3、幻读（Phantom reads）

幻读和不可重复读相似。当一个事务（T1）读取几行记录后，另一个并发事务（T2）插入了一些记录时，幻读就发生了。在后来的查询中，第一个事务（T1）就会发现一些原来没有的额外记录。

**幻读重点在新增或删除**。

在理想状态下，事务之间将完全隔离，从而可以防止这些问题发生。然而，完全隔离会影响性能，因为隔离经常涉及到锁定在数据库中的记录（甚至有时是锁表）。完全隔离要求事务相互等待来完成工作，会阻碍并发。因此，可以根据业务场景选择不同的隔离级别。

| **隔离级别**               | **含义**                                                     |
| -------------------------- | ------------------------------------------------------------ |
| ISOLATION_DEFAULT          | 使用后端数据库默认的隔离级别                                 |
| ISOLATION_READ_UNCOMMITTED | 允许读取尚未提交的更改。可能导致脏读、幻读或不可重复读。     |
| ISOLATION_READ_COMMITTED   | （Oracle 默认级别）允许从已经提交的并发事务读取。可防止脏读，但幻读和不可重复读仍可能会发生。 |
| ISOLATION_REPEATABLE_READ  | （MYSQL默认级别）对相同字段的多次读取的结果是一致的，除非数据被当前事务本身改变。可防止脏读和不可重复读，但幻读仍可能发生。 |
| ISOLATION_SERIALIZABLE     | 完全服从ACID的隔离级别，确保不发生脏读、不可重复读和幻影读。这在所有隔离级别中也是最慢的，因为它通常是通过完全锁定当前事务所涉及的数据表来完成的。 |

#### 3）只读

如果一个事务只对数据库执行读操作，那么该数据库就可能利用那个事务的只读特性，采取某些优化措施。通过把一个事务声明为只读，可以给后端数据库一个机会来应用那些它认为合适的优化措施。由于只读的优化措施是在一个事务启动时由后端数据库实施的， 因此，只有对于那些具有可能启动一个新事务的传播行为（PROPAGATION_REQUIRES_NEW、PROPAGATION_REQUIRED、 ROPAGATION_NESTED）的方法来说，将事务声明为只读才有意义。

#### 4）事务超时

为了使一个应用程序很好地执行，它的事务不能运行太长时间。因此，声明式事务的下一个特性就是它的超时。

假设事务的运行时间变得格外的长，由于事务可能涉及对数据库的锁定，所以长时间运行的事务会不必要地占用数据库资源。这时就可以声明一个事务在特定秒数后自动回滚，不必等它自己结束。

由于超时时钟在一个事务启动的时候开始的，因此，只有对于那些具有可能启动一个新事务的传播行为（PROPAGATION_REQUIRES_NEW、PROPAGATION_REQUIRED、ROPAGATION_NESTED）的方法来说，声明事务超时才有意义。

#### 5）回滚规则

在默认设置下，事务只在出现运行时异常（runtime exception）时回滚，而在出现受检查异常（checked exception）时不回滚（这一行为和EJB中的回滚行为是一致的）。
不过，可以声明在出现特定受检查异常时像运行时异常一样回滚。同样，也可以声明一个事务在出现特定的异常时不回滚，即使特定的异常是运行时异常。

#### 6）Spring声明式事务配置参考

```xml
<tx:annotation-driven transaction-manager="transactionManager"/>
<bean id="sessionFactory" class="org.springframework.orm.hibernate3.LocalSessionFactoryBean"> 
        <property name="configLocation" value="classpath:hibernate.cfg.xml" /> 
        <property name="configurationClass" value="org.hibernate.cfg.AnnotationConfiguration" />
    </bean> 
 <!-- 定义事务管理器（声明式的事务） --> 
    <bean id="transactionManager" class="org.springframework.orm.hibernate3.HibernateTransactionManager">
        <property name="sessionFactory" ref="sessionFactory" />
    </bean>
```

```java
@Transactional
@Component("userDao")
public class UserDaoImpl extends HibernateDaoSupport implements UserDao {
    public List<User> listUsers() {
        return this.getSession().createQuery("from User").list();
    }  
}
```

### 8、BeanFactory 常用实现类有哪些

DefaultListableBeanFactory、XmlBeanFactory、ApplicationContext

XmlBeanFactory 最常用，它根据 XML 文件中的定义加载 beans。该容器从 XML 文件读取配置元数据并用它去创建一个完全配置的系统或应用。

### 9、解释 Spring JDBC、Spring DAO 和 Spring ORM

#### 1）Spring JDBC

提供 jdbc 模板类，移除了连接代码以帮助你专注于 SQL 查询和相关参数。Spring-JDBC 还提供了一个 JdbcDaoSupport，这样你可以对你的 DAO 进行扩展开发。它主要定义了两个属性：一个 DataSource 和一个 JdbcTemplate，它们都可以用来实现 DAO 方法。JdbcDaoSupport 还提供了一个将 SQL 异常转换为 SpringDataAccessExceptions 的异常翻译器。 

#### 2）Spring DAO

开发规范，没有实现也没有模板，只是一个接口。

在写一个 DAO 的时候， 你应该使用 @Repository 对其进行注解，这样底层技术(JDBC，Hibernate，JPA，等等)的相关异常才能一致性地翻译为相应 的 DataAccessException 子类。

#### 3）Spring ORM

Spring-ORM 是一个囊括了很多持久层技术(JPA，JDO，Hibernate，iBatis)的总括模块。对于这些技术中的每一 个，Spring 都提供了集成类，这样每一种技术都能够在遵循 Spring 的配置原则下进行使用，并平稳地和 Spring 事 务管理进行集成。 

**对 于 每 一 种 技 术 ， 配 置 主 要 在 于 将 一 个 DataSource bean 注 入 到 某 种 SessionFactory 或 者 EntityManagerFactory 等 bean 中。纯 JDBC 不需要这样的一个集成类(JdbcTemplate 除外)，因为 JDBC 仅依 赖于一个 DataSource。** 

### 10、简单介绍一下 SpringWEB 模块

Spring 的 WEB 模块是构建在 application context 模块基础之上，提供一个适合 web 应用的上下文。这个模块 也包括支持多种面向 web 的任务，如透明地处理多个文件上传请求和程序级请求参数的绑定到你的业务对象。它也有 对 Jakarta Struts 的支持。 

### 11、Spring 配置文件有什么用

Spring 配置文件是个 XML 文件，这个文件包含了类信息，描述了如何配置它们，以及如何调用。

### 12、什么是 Spring IOC 容器

IOC 控制反转：Spring IOC 负责创建对象，管理对象。通过依赖注入（DI），装配对象，配置对象，并且管理这些对象的整个生命周期。

### 13、IOC 的优点是什么

IOC 或依赖注入把应用的代码量降到最低。最小的代价和最小的侵入性使松耦合得以实现。IOC 容器支持加载服务时的饿汉式初始化和懒加载。

### 14、ApplicationContext 的实现类有哪些

FileSystemXmlApplicationContext：此容器从一个 XML 文件中加载 beans 的定义，XMLBean 配置文件的全路径名必须提供给它的构造函数。

ClassPathXmlApplicationContext：此容器也从一个 XML 文件中加载 beans 的定义，这里，你需要正确设置 classpath 因为这个容器将在 classpath 里找 bean 配置。

WebXmlApplicationContext：此容器加载一个 XML 文件，此文件定义了一个 WEB 应用的所有 bean。

### 15、BeanFactory 与 ApplicationContext 有什么区别

#### 1）BeanFactory

基础类型的 IOC 容器，提供完整的 IOC 服务支持。如果没有特殊指定，默认采用延迟初始化策略。相对来说，容器启动初期速度较快，所需资源有限。

#### 2）ApplicationContext

ApplicationContext 是在 BeanFactory 的基础上构建，是相对比较高级的容器实现，除了 BeanFactory 的所有 支持外，ApplicationContext 还提供了事件发布、国际化支持等功能。**ApplicationContext 管理的对象，在容器启动 后默认全部初始化并且绑定完成。** 

### 16、什么是 Spring 的依赖注入

依赖类不由程序员实例化，而是通过 spring 容器帮我们 new 指定实例并且将实例注入到需要该对象的类中。

依赖注入又叫控制反转：平常我们 new 一个实例，这个实例控制权是我们程序员，而控制反转是指 new 实例工作不由我们程序员来做而是交给 spring 容器来做。

### 17、有哪些不同类型的 IOC（依赖注入）方式？

#### 1、Set 注入

#### 2、构造器注入

#### 3、静态工厂方法注入

#### 4、实力工厂方法注入

### 18、什么是 Spring beans

Spring beans 是那些形成 Spring 应用的主干的 java 对象。它们被Spring IOC 容器初始化，装配和管理。这些 beans 通过容器中配置的元数据创建。比如，以 XML 文件中 <bean/> 的形式定义。

**Spring 里的 bean 都是单例。**

### 19、一个 Spring Beans 的定义需要包含什么？

一个 Spring Bean 的定义包含容器必知的所有配置元数据，包括如何创建一个 bean，它的生命周期详情及它的 依赖。 

### 20、怎样定义类的作用域? 

当定义一个 <bean> 在 spring 里，我们还能给这个 bean 声明一个作用域。它可以通过 bean 定义中的 scope 属性来定义。

非单例 scope 的属性值为 prototype

### 21、Spring 支持的几种 bean 的作用域

#### 1）singleton 

bean 在每个 Spring ioc 容器中只有一个实例。 

#### 2）prototype

一个 bean 的定义可以有多个实例。 

#### 3）request

每次 http 请求都会创建一个 bean，该作用域仅在基于 web 的 Spring ApplicationContext 情形下有 效。 

#### 4）session

在 一 个 HTTP Session 中 ， 一 个 bean 定 义 对 应 一 个 实 例 。 该 作 用 域 仅 在 基 于 web 的 Spring ApplicationContext 情形下有效。 

#### 5）global-session

在一个全局的 HTTP Session 中，一个 bean 定义对应一个实例。该作用域仅在基于 web 的 Spring ApplicationContext 情形下有效。 

缺省的 Spring bean 的作用域是 Singleton。

### 22、 Spring 框架中的单例 bean 是线程安全的吗? 

Spring 框架中的单例 bean 不是线程安全的。

### 23、什么是 Spring 的内部 bean？

当一个 bean 仅被用作另一个 bean 的属性时，它能被声明为一个内部 bean，为了定义 inner bean，在 Spring 的基于 XML 的配置元数据中，可以在 <property/> 或 <constructor-arg/> 元素内使用 <bean/> 元素，内部 bean 通常是匿名的，它们的 Scope 一般是 prototype。

### 24、在 Spring 中如何注入一个 java 集合？

Spring 提供以下几种集合的配置元素： 

list 类型用于注入一列值，允许有相同的值。

set 类型用于注入一组值，不允许有相同的值。 

map 类型用于注入一组键值对，键和值都可以为任意类型。 

props 类型用于注入一组键值对，键和值都只能为 String 类型。 

### 25、什么是 bean 的自动装配？

无须在 Spring 配置文件中描述 javaBean 之间的依赖关系（如配置、）。IOC 容器会自动建立 javabean 之间的关联关系。

### 26、解释不同方式的自动装配

有五种自动装配的方式

#### 1）no

默认的方式是不进行自动装配，通过显式设置 ref 属性来进行装配。

#### 2）byName

通过参数名自动装配，Spring 容器在配置文件中发现 bean 的 autowire 属性被设置成 byName，之后容器试图匹配、装配和该 bean 的属性具有相同名字的 bean。

#### 3）byType

通过参数类型自动装配，Spring 容器在配置文件中发现 bean 的 autowire 属性被设置为 byType，之后容器试图匹配、装配和该 bean 的属性具有相同类型的 bean。如果有多个 bean 符合条件，则抛出错误。

#### 4）constructor

这个方法类似于 byType，但是要提供给构造器参数，如果没有确定的带参数的构造器参数类型，将会抛出错误。

#### 5）autodetect

首先尝试使用 constructor 来自动装配，如果无法工作，则使用 byType。

### 27、什么是基于 java 的 Spring 注解配置？给一些注解例子

基于 Java 的配置，允许你在少量的 java 注解的帮助下，进行你的大部分 Spring 配置而非通过 XML 文件。以 @Configuration 注解为例，它用来标记类可以当作一个 bean 定义，被 SpringIOC 容器使用。另一个例子是 @Bean 注解，它表示此方法将要返回一个对象，作为一个 bean 注册进 Spring 应用上下文。

### 28、什么是基于注解的容器配置？

相对于 XML 文件，注解型的配置依赖于通过字节码元数据装配组件，而非尖括号的声明。开发者通过在相应的类，方法或属性上使用注解的方式，直接组件类中进行配置，而不是使用 xml 表述 bean 的装配关系。

### 29、怎样开启注解装配

在 Spring 的配置文件中配置

```xml
<context:annotation-config/>
```

### 30、在 Spring 框架中如何更有效地使用 JDBC

使用 Spring 框架提供的 JdbcTemplate 模板类。

### 31、使用 Spring 通过什么方式访问 Hibernate？

在 Spring 中有两种方式访问 Hibernate： 

1）控制反转 HibernateTemplate 和 Callback。 

2）继承 HibernateDAOSupport 提供一个 AOP 拦截器。 

### 32、Spring 支持的 ORM 框架有哪些？

Spring 支持以下 ORM：

Hibernate、iBatis、JPA (Java Persistence API)、TopLink、JDO (Java Data Objects)、OJB 

### 33、简单解释一下 spring 的 AOP

AOP（Aspect Oriented Programming），即面向切面编程程，可以说是 OOP（Object Oriented Programming， 面向对象编程）的补充和完善。

OOP 允许开发者定义纵向的关系，但并不适合定义横向的关系

AOP 技术恰恰相反，它利用一种称为"横切"的技术，剖解开封装的对象内部，并将那些影响了多个类的公共行为 封装到一个可重用模块，并将其命名为"Aspect"，即切面。

使用"横切"技术，AOP 把软件系统分为两个部分：核心关注点和横切关注点。业务处理的主要流程是核心关注点， 与之关系不大的部分是横切关注点。

### 34、在 Spring AOP 中，关注点和横切关注的区别是什么？

关注点是应用中一个模块的行为，一个关注点可能会被定义成一个我们想实现的一个功能。

横切关注点是一个关 注点，此关注点是整个应用都会使用的功能，并影响整个应用，比如日志，安全和数据传输，几乎应用的每个模块都需 要的功能。因此这些都属于横切关注点。 

### 35、什么是连接点？

被拦截到的点，因为 Spring 只支持方法类型的连接点，所以在 Spring 中连接点指的就是被拦截到的方法，实际 上连接点还可以是字段或者构造器。

### 36、Spring 的通知是什么？有哪几种类型？

通知是个在方法执行前或执行后要做的动作，实际上是程序执行时要通过 SpringAOP 框架触发的代码段。

Spring 切面可以应用五种类型的通知： 

#### 1）before

前置通知，在一个方法执行前被调用。 

#### 2）after

在方法执行之后调用的通知，无论方法执行是否成功。 

#### 3）after-returning

仅当方法成功完成后执行的通知。 

#### 4）after-throwing

在方法抛出异常退出时执行的通知。 

#### 5）around

在方法执行之前和之后调用的通知。 

### 37、什么是切点？

切入点是一个或一组连接点，通知将在这些位置执行。可以通过表达式或匹配的方式指明切入点。 

### 38、什么是目标对象?

被一个或者多个切面所通知的对象。它通常是一个代理对象。也指被通知（advised）对象。

### 39、什么是代理? 

代理是通知目标对象后创建的对象。从客户端的角度看，代理对象和目标对象是一样的。 

### 40、什么是织入？什么是织入应用的不同点？

织入是将切面和到其他应用类型或对象连接或创建一个被通知对象的过程。织入可以在编译时，加载时，或运行 时完成。 