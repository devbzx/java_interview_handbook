* [JavaSE基础](#javase%E5%9F%BA%E7%A1%80)
  * [1、面向对象](#1%E9%9D%A2%E5%90%91%E5%AF%B9%E8%B1%A1)
    * [一、面向对象都有哪些特性](#%E4%B8%80%E9%9D%A2%E5%90%91%E5%AF%B9%E8%B1%A1%E9%83%BD%E6%9C%89%E5%93%AA%E4%BA%9B%E7%89%B9%E6%80%A7)
      * [1）继承](#1%E7%BB%A7%E6%89%BF)
      * [2）封装](#2%E5%B0%81%E8%A3%85)
      * [3）多态](#3%E5%A4%9A%E6%80%81)
      * [4）抽象](#4%E6%8A%BD%E8%B1%A1)
    * [2、访问权限修饰符](#2%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90%E4%BF%AE%E9%A5%B0%E7%AC%A6)
    * [3、clone](#3clone)
      * [3\.1为什么要用clone](#31%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E7%94%A8clone)
      * [3\.2new一个新对象的过程和clone一个对象的过程区别](#32new%E4%B8%80%E4%B8%AA%E6%96%B0%E5%AF%B9%E8%B1%A1%E7%9A%84%E8%BF%87%E7%A8%8B%E5%92%8Cclone%E4%B8%80%E4%B8%AA%E5%AF%B9%E8%B1%A1%E7%9A%84%E8%BF%87%E7%A8%8B%E5%8C%BA%E5%88%AB)
      * [3\.3clone对象的使用](#33clone%E5%AF%B9%E8%B1%A1%E7%9A%84%E4%BD%BF%E7%94%A8)
        * [3\.3\.1复制对象和复制引用的区别](#331%E5%A4%8D%E5%88%B6%E5%AF%B9%E8%B1%A1%E5%92%8C%E5%A4%8D%E5%88%B6%E5%BC%95%E7%94%A8%E7%9A%84%E5%8C%BA%E5%88%AB)
        * [3\.3\.2深拷贝和浅拷贝](#332%E6%B7%B1%E6%8B%B7%E8%B4%9D%E5%92%8C%E6%B5%85%E6%8B%B7%E8%B4%9D)
  * [二、JavaSE语法](#%E4%BA%8Cjavase%E8%AF%AD%E6%B3%95)
    * [1、goto](#1goto)
    * [2、&amp;和&amp;&amp;的区别](#2%E5%92%8C%E7%9A%84%E5%8C%BA%E5%88%AB)
    * [3、跳出多重嵌套循环](#3%E8%B7%B3%E5%87%BA%E5%A4%9A%E9%87%8D%E5%B5%8C%E5%A5%97%E5%BE%AA%E7%8E%AF)
    * [4、hashCode与值](#4hashcode%E4%B8%8E%E5%80%BC)
    * [5、是否可以继承String](#5%E6%98%AF%E5%90%A6%E5%8F%AF%E4%BB%A5%E7%BB%A7%E6%89%BFstring)
    * [6、值传递](#6%E5%80%BC%E4%BC%A0%E9%80%92)
    * [7、重载（overload）和重写（override）](#7%E9%87%8D%E8%BD%BDoverload%E5%92%8C%E9%87%8D%E5%86%99override)
      * [重载的规则](#%E9%87%8D%E8%BD%BD%E7%9A%84%E8%A7%84%E5%88%99)
      * [重写的规则](#%E9%87%8D%E5%86%99%E7%9A%84%E8%A7%84%E5%88%99)
    * [8、为什么函数不能根据返回类型来区分重载](#8%E4%B8%BA%E4%BB%80%E4%B9%88%E5%87%BD%E6%95%B0%E4%B8%8D%E8%83%BD%E6%A0%B9%E6%8D%AE%E8%BF%94%E5%9B%9E%E7%B1%BB%E5%9E%8B%E6%9D%A5%E5%8C%BA%E5%88%86%E9%87%8D%E8%BD%BD)
    * [9、char能不能存汉字](#9char%E8%83%BD%E4%B8%8D%E8%83%BD%E5%AD%98%E6%B1%89%E5%AD%97)
    * [10、抽象类与接口](#10%E6%8A%BD%E8%B1%A1%E7%B1%BB%E4%B8%8E%E6%8E%A5%E5%8F%A3)
      * [不同](#%E4%B8%8D%E5%90%8C)
        * [抽象类](#%E6%8A%BD%E8%B1%A1%E7%B1%BB)
        * [接口](#%E6%8E%A5%E5%8F%A3)
      * [相同](#%E7%9B%B8%E5%90%8C)
    * [11、抽象的方法](#11%E6%8A%BD%E8%B1%A1%E7%9A%84%E6%96%B9%E6%B3%95)
      * [是否可以同时是静态的](#%E6%98%AF%E5%90%A6%E5%8F%AF%E4%BB%A5%E5%90%8C%E6%97%B6%E6%98%AF%E9%9D%99%E6%80%81%E7%9A%84)
      * [是否可同时是本地方法](#%E6%98%AF%E5%90%A6%E5%8F%AF%E5%90%8C%E6%97%B6%E6%98%AF%E6%9C%AC%E5%9C%B0%E6%96%B9%E6%B3%95)
      * [是否可同时被synchronized](#%E6%98%AF%E5%90%A6%E5%8F%AF%E5%90%8C%E6%97%B6%E8%A2%ABsynchronized)
    * [12、静态变量和实例变量](#12%E9%9D%99%E6%80%81%E5%8F%98%E9%87%8F%E5%92%8C%E5%AE%9E%E4%BE%8B%E5%8F%98%E9%87%8F)
      * [静态变量](#%E9%9D%99%E6%80%81%E5%8F%98%E9%87%8F)
      * [实例变量](#%E5%AE%9E%E4%BE%8B%E5%8F%98%E9%87%8F)
    * [13、==和equals的区别](#13%E5%92%8Cequals%E7%9A%84%E5%8C%BA%E5%88%AB)
    * [14、break和continue的区别](#14break%E5%92%8Ccontinue%E7%9A%84%E5%8C%BA%E5%88%AB)
  * [三、Java中的多态](#%E4%B8%89java%E4%B8%AD%E7%9A%84%E5%A4%9A%E6%80%81)
    * [1、java中实现多态的机制是什么](#1java%E4%B8%AD%E5%AE%9E%E7%8E%B0%E5%A4%9A%E6%80%81%E7%9A%84%E6%9C%BA%E5%88%B6%E6%98%AF%E4%BB%80%E4%B9%88)
  * [四、Java的异常处理](#%E5%9B%9Bjava%E7%9A%84%E5%BC%82%E5%B8%B8%E5%A4%84%E7%90%86)
    * [1、java中异常类分为哪些种类](#1java%E4%B8%AD%E5%BC%82%E5%B8%B8%E7%B1%BB%E5%88%86%E4%B8%BA%E5%93%AA%E4%BA%9B%E7%A7%8D%E7%B1%BB)
      * [1）按异常需要处理的时机分为](#1%E6%8C%89%E5%BC%82%E5%B8%B8%E9%9C%80%E8%A6%81%E5%A4%84%E7%90%86%E7%9A%84%E6%97%B6%E6%9C%BA%E5%88%86%E4%B8%BA)
        * [Checked异常处理方法有两种：](#checked%E5%BC%82%E5%B8%B8%E5%A4%84%E7%90%86%E6%96%B9%E6%B3%95%E6%9C%89%E4%B8%A4%E7%A7%8D)
          * [1 当前方法知道如何处理该异常](#1-%E5%BD%93%E5%89%8D%E6%96%B9%E6%B3%95%E7%9F%A5%E9%81%93%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86%E8%AF%A5%E5%BC%82%E5%B8%B8)
          * [2 当前方法不知道如何处理](#2-%E5%BD%93%E5%89%8D%E6%96%B9%E6%B3%95%E4%B8%8D%E7%9F%A5%E9%81%93%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86)
        * [Runtime异常](#runtime%E5%BC%82%E5%B8%B8)
    * [2、Error和Exception的区别](#2error%E5%92%8Cexception%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [区别](#%E5%8C%BA%E5%88%AB)
      * [Exception 类](#exception-%E7%B1%BB)
        * [运行时异常（Runtime Exception）](#%E8%BF%90%E8%A1%8C%E6%97%B6%E5%BC%82%E5%B8%B8runtime-exception)
        * [受检查的异常(Checked Exception )](#%E5%8F%97%E6%A3%80%E6%9F%A5%E7%9A%84%E5%BC%82%E5%B8%B8checked-exception-)
    * [3、java异常处理机制](#3java%E5%BC%82%E5%B8%B8%E5%A4%84%E7%90%86%E6%9C%BA%E5%88%B6)
      * [Java为系统异常和普通异常提供了不同的解决方案](#java%E4%B8%BA%E7%B3%BB%E7%BB%9F%E5%BC%82%E5%B8%B8%E5%92%8C%E6%99%AE%E9%80%9A%E5%BC%82%E5%B8%B8%E6%8F%90%E4%BE%9B%E4%BA%86%E4%B8%8D%E5%90%8C%E7%9A%84%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
        * [普通异常](#%E6%99%AE%E9%80%9A%E5%BC%82%E5%B8%B8)
        * [系统异常](#%E7%B3%BB%E7%BB%9F%E5%BC%82%E5%B8%B8)
    * [4、常见的RuntimeException](#4%E5%B8%B8%E8%A7%81%E7%9A%84runtimeexception)
      * [1）NullPointerException](#1nullpointerexception)
      * [2）ClassNotFoundException](#2classnotfoundexception)
      * [3）NumberFormatException](#3numberformatexception)
      * [4）IndexOutOfBoundsException](#4indexoutofboundsexception)
      * [5）IllegalArgumentException](#5illegalargumentexception)
      * [6）ClassCastException](#6classcastexception)
      * [7）NoClassDefFoundException](#7noclassdeffoundexception)
      * [8）SQLException](#8sqlexception)
      * [9） InstantiationException](#9-instantiationexception)
      * [10）NoSuchMethodException](#10nosuchmethodexception)
    * [5、throw和throws的区别](#5throw%E5%92%8Cthrows%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [throw](#throw)
      * [throws](#throws)
    * [6、final、finally、finalize的区别](#6finalfinallyfinalize%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [1）final](#1final)
      * [2）finally](#2finally)
      * [3）finalize](#3finalize)
  * [五、JavaSE常用的API](#%E4%BA%94javase%E5%B8%B8%E7%94%A8%E7%9A%84api)
    * [1、Math\.round()](#1mathround)
    * [2、switch()](#2switch)
    * [3、数组用没有length()方法？String有没有length()方法？](#3%E6%95%B0%E7%BB%84%E7%94%A8%E6%B2%A1%E6%9C%89length%E6%96%B9%E6%B3%95string%E6%9C%89%E6%B2%A1%E6%9C%89length%E6%96%B9%E6%B3%95)
    * [4、String、StringBuffer、StringBuilder区别](#4stringstringbufferstringbuilder%E5%8C%BA%E5%88%AB)
    * [5、String中的 ==](#5string%E4%B8%AD%E7%9A%84-)
    * [6、Java 中的日期和时间](#6java-%E4%B8%AD%E7%9A%84%E6%97%A5%E6%9C%9F%E5%92%8C%E6%97%B6%E9%97%B4)
  * [六、Java 的数据类型](#%E5%85%ADjava-%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B)
    * [1、基本数据类型及其占的字节数](#1%E5%9F%BA%E6%9C%AC%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%8F%8A%E5%85%B6%E5%8D%A0%E7%9A%84%E5%AD%97%E8%8A%82%E6%95%B0)
    * [2、String是基本数据类型吗](#2string%E6%98%AF%E5%9F%BA%E6%9C%AC%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%90%97)
    * [3、关于short](#3%E5%85%B3%E4%BA%8Eshort)
    * [4、基本类型对应的包装类](#4%E5%9F%BA%E6%9C%AC%E7%B1%BB%E5%9E%8B%E5%AF%B9%E5%BA%94%E7%9A%84%E5%8C%85%E8%A3%85%E7%B1%BB)
    * [5、Integer 的比较](#5integer-%E7%9A%84%E6%AF%94%E8%BE%83)
    * [6、String的常用方法](#6string%E7%9A%84%E5%B8%B8%E7%94%A8%E6%96%B9%E6%B3%95)
      * [1）length()](#1length)
      * [2）indexOf(int ch)](#2indexofint-ch)
      * [3）indexOf(String str)](#3indexofstring-str)
      * [4）lastIndexOf(int ch)](#4lastindexofint-ch)
      * [5）indexOf(String str)](#5indexofstring-str)
      * [6）subString(int beginIndex)](#6substringint-beginindex)
      * [7）subString(int beginIndex, int endIndex)](#7substringint-beginindex-int-endindex)
      * [8）trim()](#8trim)
      * [9）equals(Object obj)](#9equalsobject-obj)
      * [10）toLowerCase()](#10tolowercase)
      * [11）toUpperCase()](#11touppercase)
      * [12）charAt(int index)](#12charatint-index)
      * [13）split(String regex , int limit)](#13splitstring-regex--int-limit)
      * [14）getBytes()](#14getbytes)
  * [七、Java 的IO](#%E4%B8%83java-%E7%9A%84io)
    * [1、java 中的流](#1java-%E4%B8%AD%E7%9A%84%E6%B5%81)
      * [按流的方向](#%E6%8C%89%E6%B5%81%E7%9A%84%E6%96%B9%E5%90%91)
      * [按处理数据的单位](#%E6%8C%89%E5%A4%84%E7%90%86%E6%95%B0%E6%8D%AE%E7%9A%84%E5%8D%95%E4%BD%8D)
    * [2、字节流如何转为字符流](#2%E5%AD%97%E8%8A%82%E6%B5%81%E5%A6%82%E4%BD%95%E8%BD%AC%E4%B8%BA%E5%AD%97%E7%AC%A6%E6%B5%81)
      * [输入流](#%E8%BE%93%E5%85%A5%E6%B5%81)
      * [输出流](#%E8%BE%93%E5%87%BA%E6%B5%81)
    * [3、将对象序列化到文件](#3%E5%B0%86%E5%AF%B9%E8%B1%A1%E5%BA%8F%E5%88%97%E5%8C%96%E5%88%B0%E6%96%87%E4%BB%B6)
    * [4、字节流和字符流的区别](#4%E5%AD%97%E8%8A%82%E6%B5%81%E5%92%8C%E5%AD%97%E7%AC%A6%E6%B5%81%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [字节流](#%E5%AD%97%E8%8A%82%E6%B5%81)
      * [字符流](#%E5%AD%97%E7%AC%A6%E6%B5%81)
    * [5、通过序列化克隆对象](#5%E9%80%9A%E8%BF%87%E5%BA%8F%E5%88%97%E5%8C%96%E5%85%8B%E9%9A%86%E5%AF%B9%E8%B1%A1)
    * [6、什么是java序列化，如何实现java序列化](#6%E4%BB%80%E4%B9%88%E6%98%AFjava%E5%BA%8F%E5%88%97%E5%8C%96%E5%A6%82%E4%BD%95%E5%AE%9E%E7%8E%B0java%E5%BA%8F%E5%88%97%E5%8C%96)
  * [八、Java 的集合](#%E5%85%ABjava-%E7%9A%84%E9%9B%86%E5%90%88)
    * [1、HashMap 排序](#1hashmap-%E6%8E%92%E5%BA%8F)
    * [2、集合安全性问题](#2%E9%9B%86%E5%90%88%E5%AE%89%E5%85%A8%E6%80%A7%E9%97%AE%E9%A2%98)
    * [3、ArrayList 内部用什么实现的？](#3arraylist-%E5%86%85%E9%83%A8%E7%94%A8%E4%BB%80%E4%B9%88%E5%AE%9E%E7%8E%B0%E7%9A%84)
    * [4、并发集合和普通集合如何区别？](#4%E5%B9%B6%E5%8F%91%E9%9B%86%E5%90%88%E5%92%8C%E6%99%AE%E9%80%9A%E9%9B%86%E5%90%88%E5%A6%82%E4%BD%95%E5%8C%BA%E5%88%AB)
    * [5、List 的三个子类的特点](#5list-%E7%9A%84%E4%B8%89%E4%B8%AA%E5%AD%90%E7%B1%BB%E7%9A%84%E7%89%B9%E7%82%B9)
    * [6、List 和 Map、Set 的区别](#6list-%E5%92%8C-mapset-%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [6\.1 结构特点](#61-%E7%BB%93%E6%9E%84%E7%89%B9%E7%82%B9)
      * [6\.2 实现类](#62-%E5%AE%9E%E7%8E%B0%E7%B1%BB)
        * [List 接口有三个实现类](#list-%E6%8E%A5%E5%8F%A3%E6%9C%89%E4%B8%89%E4%B8%AA%E5%AE%9E%E7%8E%B0%E7%B1%BB)
        * [Map 接口有三个实现类](#map-%E6%8E%A5%E5%8F%A3%E6%9C%89%E4%B8%89%E4%B8%AA%E5%AE%9E%E7%8E%B0%E7%B1%BB)
        * [Set 接口有两个实现类](#set-%E6%8E%A5%E5%8F%A3%E6%9C%89%E4%B8%A4%E4%B8%AA%E5%AE%9E%E7%8E%B0%E7%B1%BB)
      * [6\.3 区别](#63-%E5%8C%BA%E5%88%AB)
    * [7、HashMap 和 HashTable 有什么区别？](#7hashmap-%E5%92%8C-hashtable-%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB)
    * [8、数组和链表分别比较适合用于什么场景，为什么？](#8%E6%95%B0%E7%BB%84%E5%92%8C%E9%93%BE%E8%A1%A8%E5%88%86%E5%88%AB%E6%AF%94%E8%BE%83%E9%80%82%E5%90%88%E7%94%A8%E4%BA%8E%E4%BB%80%E4%B9%88%E5%9C%BA%E6%99%AF%E4%B8%BA%E4%BB%80%E4%B9%88)
      * [区别](#%E5%8C%BA%E5%88%AB-1)
        * [数组是将元素在内存中连续存储的；](#%E6%95%B0%E7%BB%84%E6%98%AF%E5%B0%86%E5%85%83%E7%B4%A0%E5%9C%A8%E5%86%85%E5%AD%98%E4%B8%AD%E8%BF%9E%E7%BB%AD%E5%AD%98%E5%82%A8%E7%9A%84)
          * [它的优点](#%E5%AE%83%E7%9A%84%E4%BC%98%E7%82%B9)
          * [它的缺点](#%E5%AE%83%E7%9A%84%E7%BC%BA%E7%82%B9)
        * [链表是动态申请内存空间](#%E9%93%BE%E8%A1%A8%E6%98%AF%E5%8A%A8%E6%80%81%E7%94%B3%E8%AF%B7%E5%86%85%E5%AD%98%E7%A9%BA%E9%97%B4)
      * [应用场景](#%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF)
        * [数组应用场景](#%E6%95%B0%E7%BB%84%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF)
        * [链表应用场景](#%E9%93%BE%E8%A1%A8%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF)
      * [面试题](#%E9%9D%A2%E8%AF%95%E9%A2%98)
    * [9、Java 中 ArrayList 和 LinkedList 区别？](#9java-%E4%B8%AD-arraylist-%E5%92%8C-linkedlist-%E5%8C%BA%E5%88%AB)
    * [10、List a = new ArrayList() 和 ArrayList a =new ArrayList()的区别？](#10list-a--new-arraylist-%E5%92%8C-arraylist-a-new-arraylist%E7%9A%84%E5%8C%BA%E5%88%AB)
    * [11、要对集合操作时，比较ArrayList 和 LinkedList](#11%E8%A6%81%E5%AF%B9%E9%9B%86%E5%90%88%E6%93%8D%E4%BD%9C%E6%97%B6%E6%AF%94%E8%BE%83arraylist-%E5%92%8C-linkedlist)
    * [12、请用两个队列模拟堆栈结构。](#12%E8%AF%B7%E7%94%A8%E4%B8%A4%E4%B8%AA%E9%98%9F%E5%88%97%E6%A8%A1%E6%8B%9F%E5%A0%86%E6%A0%88%E7%BB%93%E6%9E%84)
    * [13、Collection 和 Map 的集成体系](#13collection-%E5%92%8C-map-%E7%9A%84%E9%9B%86%E6%88%90%E4%BD%93%E7%B3%BB)
    * [14、Map 中的 key 和 value 可以为 null 么？](#14map-%E4%B8%AD%E7%9A%84-key-%E5%92%8C-value-%E5%8F%AF%E4%BB%A5%E4%B8%BA-null-%E4%B9%88)
  * [九、java 的多线程](#%E4%B9%9Djava-%E7%9A%84%E5%A4%9A%E7%BA%BF%E7%A8%8B)
    * [1、程序、进程、线程基本概念](#1%E7%A8%8B%E5%BA%8F%E8%BF%9B%E7%A8%8B%E7%BA%BF%E7%A8%8B%E5%9F%BA%E6%9C%AC%E6%A6%82%E5%BF%B5)
    * [2、并行和并发](#2%E5%B9%B6%E8%A1%8C%E5%92%8C%E5%B9%B6%E5%8F%91)
    * [3、多线程的优点](#3%E5%A4%9A%E7%BA%BF%E7%A8%8B%E7%9A%84%E4%BC%98%E7%82%B9)
    * [4、线程的创建和使用](#4%E7%BA%BF%E7%A8%8B%E7%9A%84%E5%88%9B%E5%BB%BA%E5%92%8C%E4%BD%BF%E7%94%A8)
      * [1）传统使用类 Thread 和接口 Runnable 实现](#1%E4%BC%A0%E7%BB%9F%E4%BD%BF%E7%94%A8%E7%B1%BB-thread-%E5%92%8C%E6%8E%A5%E5%8F%A3-runnable-%E5%AE%9E%E7%8E%B0)
        * [继承 Thread 类](#%E7%BB%A7%E6%89%BF-thread-%E7%B1%BB)
        * [实现 Runnable 接口](#%E5%AE%9E%E7%8E%B0-runnable-%E6%8E%A5%E5%8F%A3)
      * [2）JDK5\.0新增线程创建方式](#2jdk50%E6%96%B0%E5%A2%9E%E7%BA%BF%E7%A8%8B%E5%88%9B%E5%BB%BA%E6%96%B9%E5%BC%8F)
        * [实现 Callable 接口](#%E5%AE%9E%E7%8E%B0-callable-%E6%8E%A5%E5%8F%A3)
          * [特点](#%E7%89%B9%E7%82%B9)
        * [使用线程池](#%E4%BD%BF%E7%94%A8%E7%BA%BF%E7%A8%8B%E6%B1%A0)
          * [特点](#%E7%89%B9%E7%82%B9-1)
  * [十、Java 内部类](#%E5%8D%81java-%E5%86%85%E9%83%A8%E7%B1%BB)
    * [1、静态嵌套类（static nested class）和内部类（inner class）的不同](#1%E9%9D%99%E6%80%81%E5%B5%8C%E5%A5%97%E7%B1%BBstatic-nested-class%E5%92%8C%E5%86%85%E9%83%A8%E7%B1%BBinner-class%E7%9A%84%E4%B8%8D%E5%90%8C)
      * [静态嵌套类](#%E9%9D%99%E6%80%81%E5%B5%8C%E5%A5%97%E7%B1%BB)
      * [内部类](#%E5%86%85%E9%83%A8%E7%B1%BB)
    * [2、下面代码哪些地方会产生编译错误](#2%E4%B8%8B%E9%9D%A2%E4%BB%A3%E7%A0%81%E5%93%AA%E4%BA%9B%E5%9C%B0%E6%96%B9%E4%BC%9A%E4%BA%A7%E7%94%9F%E7%BC%96%E8%AF%91%E9%94%99%E8%AF%AF)

# JavaSE基础

## 1、面向对象

### 一、面向对象都有哪些特性

#### 1）继承

​		从已有类得到继承信息创建新类的过程。提供继承信息的类被称为父类（超类、基类）；得到继承信息的称为子类（派生类）。让变化的软件系统有了延续性，也是封装程序中可变因素的重要手段。

#### 2）封装

​		将数据和操作数据的方法绑定起来，对数据的访问只能通过已定义的接口。封装就是隐藏一切可以隐藏的东西，只向外界提供最简单的编程接口。

#### 3）多态

​		指允许不同子类型的对象对同一消息做出的不同响应。简单说就是对象调用同样的方法去做不同的事。分为编译时多态和运行时多态。方法重载是编译时多态（前绑定），方法重写是运行时多态（后绑定）。运行时多态是面向对象最精髓的东西，实现多态：方法重写（子类继承父类并重写方法）；对象造型（父类引用子类对象，同样的引用同样的方法就会根据子类对象的不同而表现出来不同的行为）。

#### 4）抽象

​		将对象的共同特征总结出来构造类的过程，包括数据抽象和行为抽象。只关注对象有哪些行为，不关注这些行为描述细节是什么。

**注意：**默认三大特性只有继承、封装、多态

### 2、访问权限修饰符

public、private、protected、default区别

public>protected(其他包不能)>default(包权限，本包内)>private(只有当前类)

### 3、clone

#### 3.1为什么要用clone

​		对象A中包含了一些有效值，我们需要一个与A完全相同的对象B，并且B的改动不会影响A的值。也就是说A、B是两个独立对象，但B的初始值是A确定的，在java中简单的赋值语句不能满足。要实现这个需求有许多途径，但是clone()方法是其中最简单，也是最高效的手段。

#### 3.2new一个新对象的过程和clone一个对象的过程区别

​		new的本意是分配内存。执行到new时先看new操作符后面的类型，因为知道了类型才能知道要分配多大的内存空间。分配完后调用构造函数填充对象的各个域，这个过程叫做对象的初始化，构造方法返回后，对象创建完毕，可以把它的引用(地址)发布到外部，在外部就可以使用这个引用操纵这个对象。

​		clone第一步分配内存，调用clone方法时，分配内存和原对象（即调用clone方法的对象）相同，然后使用原对象中对应的各个域填充新对象的各个域，填充完成后clone方法返回，一个新对象被创建，同样可以把这个对象的引用发布到外部。

#### 3.3clone对象的使用

##### 3.3.1复制对象和复制引用的区别

引用的复制

```java
1. Person p = new Person(23, "zhang");
2. Person p1 = p;
3. System.out.println(p);
4. System.out.println(p1);
```

```java
1．com.itheima.Person@2f9ee1ac
2．com.itheima.Person@2f9ee1ac 
```

克隆

```java
1．Person p = new Person(23, "zhang"); 
2．Person p1 = (Person) p.clone();
3．System.out.println(p);
4．System.out.println(p1); 
```

克隆也是new了一个对象

```java
1. com.itheima.Person@2f9ee1ac
2. com.itheima.Person@67f1fba0 
```

##### 3.3.2深拷贝和浅拷贝

浅拷贝将引用类型的引用赋给了另一个对象，而深拷贝则是创建了一个新的引用类型并赋给了新对象。

clone是浅拷贝

实现深拷贝

```java
1．static class Body implements Cloneable{
2． 	public Head head;
3． 	public Body() {}
4． 	public Body(Head head) {this.head = head;}
5． 	@Override
6． 	protected Object clone() throws CloneNotSupportedException{ 
7． 	Body newBody = (Body) super.clone();
8． 	newBody.head = (Head) head.clone();
9． 	return newBody;
10． }
11．}
12．static class Head implements Cloneable{ 
13． public Face face;
14． public Head() {}
15． @Override
16． protected Object clone() throws CloneNotSupportedException{ 
17． return super.clone();
18． } }
19．public static void main(String[] args) throws CloneNotSupportedException{ 
20． Body body = new Body(new Head(new Face()));
21． Body body1 = (Body) body.clone();
22． System.out.println("body == body1 : " + (body == body1) );
23． System.out.println("body.head == body1.head : " + (body.head == body1.head));
24．} 
```

打印结果

```java
1. body == body1 : false
2. body.head == body1.head : false 
```

## 二、JavaSE语法

### 1、goto

java中没有goto语句，goto、const为保留字

### 2、&和&&的区别

&：按位与；逻辑与。左右为true才为true

&&：短路与运算。左右为true才为true

&&左边表达式为false的话后边直接短路。

### 3、跳出多重嵌套循环

在最外层添加标记A，break A; 可以跳出多重循环。

### 4、hashCode与值

两个对象值相等但是hashCode一定相等，两个对象hashCode相等值不一定相等。

### 5、是否可以继承String

String是final类

```java
public final class String
    implements java.io.Serializable, Comparable<String>, CharSequence {
```

### 6、值传递

​		当一个对象被当作参数传递到一个方法后，此方法可改变这个对象的属性， 并 可返回变化后的结果，是值传递。

​		Java 语言的方法调用只支持参数的值传递。当一个对象实例作为一个参数被传递到方法中时，参数的 值就是对该对象的引用。对象的属性可以在被调用过程中被改变，但对对象引用的改变是不会影响到调用者的。

### 7、重载（overload）和重写（override）

重载是编译时的多态，重写是运行时的多态。

#### 重载的规则

1.方法名一致，参数列表中参数的顺序，类型，个数不同。

2.重载与方法的返回值无关，存在于父类和子类，同类中。

3.可以抛出不同异常，可以有不同修饰符。

#### 重写的规则

1、参数列表必须完全与被重写方法一致，返回类型必须完全与被重写方法的返回类型一致。

2、构造方法不能被重写，声明为final的方法不能被重写，声明为static的方法不能被重写，但是能够被再次声明。

3、访问权限不能比父类中被重写的方法的访问权限更低。

4、重写的方法能够抛出任何非强制异常（UncheckedException，也叫非运行时异常），无论被重写的方法是 否抛出异常。但是，重写的方法不能抛出新的强制性异常，或者比被重写方法声明的更广泛的强制性异常，反之则 可以。 

### 8、为什么函数不能根据返回类型来区分重载

因为调用时不能指定类型的信息

```java
1．float max(int a, int b);
2．int max(int a, int b); 
```

当调用max时无法确定调用哪个。

函数的返回值只是作为函数运行之后的一个“状态”，他是保持方法的调用者与被调用者进行通信的关键。并不能 作为某个方法的“标识”。 

### 9、char能不能存汉字

char可以存储一个汉字，java使用unicode编码，一个char类型占两个字节（16比特），放一个中文没问题。

使用unicode意味在jvm内部和外部有不同表现形式，内部是unicode，在外部时需要编码转换。

### 10、抽象类与接口

#### 不同

##### 抽象类

1、抽象类可以定义构造器

2、可以有抽象方法和具体方法

3、抽象类中成员可以是 private、默认、protected、 public

4、抽象类中可以定义成员变量

5、有抽象方法的类必须声明为抽象类，而抽象类未必要有抽象方法

6、抽象类中可以包含静态方法

7、一个类只能继承一个抽象类

##### 接口

1、接口中不能定义构造器

2、方法全为抽象方法

3、接口中成员全部是public

4、接口中定义的成员变量实际上都是常量

5、接口中不允许有静态方法

6、一个类中可以实现多个接口

#### 相同

1.不能够实例化 

2.可以将抽象类和接口类型作为引用类型  29 

3.一个类如果继承了某个抽象类或者实现了某个接口都需要对其中的抽象方法全部进行实现，否则该类仍然需要 被声明为抽象类 

### 11、抽象的方法

#### 是否可以同时是静态的

不能，抽象方法需要子类重写，静态方法无法被重写。

#### 是否可同时是本地方法

本地方法是由本地代码实现的方法，而抽象方法是没有实现的。

#### 是否可同时被synchronized

synchronized和方法的实现细节有关，抽象方法不涉及实现细节。

### 12、静态变量和实例变量

#### 静态变量

被static修饰的变量也叫类变量。属于类，不属于类的任何一个对象，不管这个类创建多少个对象，静态变量在内存中有且仅有一个拷贝。

静态变量可以实现让多个对象共享内存。

#### 实例变量

必须依存于某一实例，需要先创建对象然后通过对象才能访问到它。

### 13、==和equals的区别

==是运算符，equals是方法

==若比较基本类型比较数值是否相同，比较对象比较地址是否相同

equals比较对象内容是否相同

### 14、break和continue的区别

break和continue都是控制循环的语句

break用来结束循环，跳出循环执行循环外的语句

continue执行后跳出此次循环，执行下次循环

## 三、Java中的多态

### 1、java中实现多态的机制是什么

父类或接口定义的引用变量可以指向子类或具体实现类的实例对象，程序调用的方法在运行期才动态绑定，就是引用变量所指向的具体实例对象的方法，也就是内存里正在运行的那个对象的方法，而不是引用变量类型中定义的方法。

## 四、Java的异常处理

### 1、java中异常类分为哪些种类

#### 1）按异常需要处理的时机分为

编译时异常（也叫强制性异常）也叫CheckedException。

运行时异常（也叫非强制性异常）也叫RuntimeException。

##### Checked异常处理方法有两种：

###### 1 当前方法知道如何处理该异常

则用try...catch块来处理该异常。

###### 2 当前方法不知道如何处理

则在定义该方法时声明抛出该异常。运行时异常只有当前代码在运行时才发生的异常，编译时不需要try catch。

##### Runtime异常

如除数是 0 和数组下标越界等，其产生频繁，处理麻烦，若显示申明或者捕获将会对程序的可读性和运行效率影响很大。

所以由系统自动检测并将它们交给缺省的异常处理程序。当然如果你有处理要求 也可以显示捕获它们。

### 2、Error和Exception的区别

父类都是Throwable

#### 区别

Error 类一般是指与虚拟机相关的问题，如系统崩溃，虚拟机错误，内存空间不足，方法调用栈溢出等。对于这类 错误的导致的应用程序中断，仅靠程序本身无法恢复和和预防，遇到这样的错误，建议让程序终止。

Exception 类表示程序可以处理的异常，可以捕获并且可能恢复。遇到此类异常，应尽可能处理异常，使程序恢复运行，而不是随意终止异常。

#### Exception 类

##### 运行时异常（Runtime Exception）

ArithmaticException,IllegalArgumentException，编译能通过，但是一运行就终止了，程序不会处理运行时异常， 出现这类异常，程序会终止

##### 受检查的异常(Checked Exception )

要么用 try。。。catch 捕获，要么用 throws 字句声明抛出，交给它 的父类处理，否则编译不会通过。

### 3、java异常处理机制

java对异常进行了分类，不同异常用不同的java类表示，所有异常的根类为java.lang.Throwable。

#### Java为系统异常和普通异常提供了不同的解决方案

##### 普通异常

编译器强制普通异常必须try ... catch处理或用throws声明继续抛给上层调用方法处理，所以普通异常也称为checked异常

##### 系统异常

可以处理也可以不处理

### 4、常见的RuntimeException

nullpointer、classnotfound、indexoutofbounds、classcast、numberformat、illegalargument、sql、nosuchmethod、noclassdeffound（本人速记）

#### 1）NullPointerException 

​		java.lang.NullPointerException空指针异常：出现原因：调用了未经初始化的对象或者是不存在的对象。

#### 2）ClassNotFoundException 

​		java.lang.ClassNotFoundException指定的类找不到：出现原因：类的名称和路径加载错误；通常都是程序 试图通过字符串	来加载某个类时可能引发异常。

#### 3）NumberFormatException 

​		java.lang.NumberFormatException字符串转换为数字异常：出现原因：字符型数据中包含非数字型字符。

#### 4）IndexOutOfBoundsException 

​		java.lang.IndexOutOfBoundsException数组角标越界异常：常见于操作数组对象时发生。 

#### 5）IllegalArgumentException 

​		java.lang.IllegalArgumentException方法传递参数错误。

#### 6）ClassCastException 

​		java.lang.ClassCastException数据类型转换异常。 

#### 7）NoClassDefFoundException 

​		java.lang.NoClassDefFoundException未找到类定义错误。 

#### 8）SQLException 

​		SQL 异常，常见于操作数据库时的 SQL 语句错误。 

#### 9） InstantiationException 

​		 java.lang.InstantiationException实例化异常。 

#### 10）NoSuchMethodException 

​		java.lang.NoSuchMethodException方法不存在异常。 

### 5、throw和throws的区别

#### throw

1）throw语句用在方法体内，表示抛出异常，由方法体内的语句处理。

2）throw是具体向外抛出异常的动作，所以它抛出的是一个异常实例，执行throw一定是抛出了某种异常。

#### throws

1）throws语句是用在方法声明后面，表示如果抛出异常，由该方法的调用者来进行异常的处理。

2）throws主要声明这个方法会抛出某种类型的异常，让它的使用者知道需要捕获的异常的类型。

3）throws表示出现异常的一种可能性，并不一定会发生这种异常。

### 6、final、finally、finalize的区别

#### 1）final

用于声明属性、方法和类，分别表示属性不可变，方法不可覆盖，被其修饰的类不可继承。

#### 2）finally

异常处理语句结构的一部分，表示总是执行

#### 3）finalize

Object类的一个方法，垃圾回收器执行时会调用被回收对象的此方法，可以覆盖此方法提供垃圾收集时的其他资源回收（关闭文件等）。当该方法被调用则代表该对象即将”死亡“，这是个被动方法，不需要我们调用。

## 五、JavaSE常用的API

### 1、Math.round()

四舍五入取整（负数的.5向绝对值小的地方转，正数的.5向绝对值大的地方转，其余数向接近的地方转）

示例

```java
System.out.println("Math.round(-22.6):"+Math.round(-22.6));
System.out.println("Math.round(-22.5):"+Math.round(-22.5));
System.out.println("Math.round(-22.4):"+Math.round(-22.4));
System.out.println("Math.round(22.6):"+Math.round(22.6));
System.out.println("Math.round(22.5):"+Math.round(22.5));
System.out.println("Math.round(22.4):"+Math.round(22.4));
```

结果

```java
Math.round(-22.6):-23
Math.round(-22.5):-22
Math.round(-22.4):-22
Math.round(22.6):23
Math.round(22.5):23
Math.round(22.4):22
```

### 2、switch()

Java 5.0以前只能用byte、short、char、int

Java 5.0开始java引入了枚举类型，所以可以用enum类型

Java 7.0开始可以使用字符串

总结

byte、short、char、int、enum、String

### 3、数组用没有length()方法？String有没有length()方法？

数组没有length()方法，有length属性。

```java
int[] ints = new int[10];
int length = ints.length;
```

String有length()方法。

```java
String s = "";
int length = s.length();
System.out.println(length);
```

### 4、String、StringBuffer、StringBuilder区别

都可以储存和操作字符串

1）String 是只读字符串、字符串常量，其引用的字符串的内容不能被改变。若修改，等于重新生成新的字符串对象。

StringBuilder、StringBuffer表示的字符串对象可以直接进行修改。每次操作都是对 StringBuilder、StringBuffer 对象本身进行修改，不是生成新的对 象；

2）String：对象定义后不可变，线程安全。

 StringBuffer：是线程安全的（对调用方法加入同步锁），执行效率 较慢，适用于多线程下操作字符串缓冲区。

StringBuilder：是线程不安全的，适用于单线程下操作字符串缓冲区大量数据。 

StringBuilder 是Java 5中引入的，它和StringBuffer 的方法完全相同，它是单线程下使用的，它的所有方法没被synchronized修饰，因此它的效率比StringBuffer高。

3）共同点

StringBuilder 与 StringBuffer 有公共父类 AbstractStringBuilder(抽象类)。 StringBuilder、StringBuffer 的方法都会调用 AbstractStringBuilder 中的公共方法，如 super.append(...)。 只是 StringBuffer 会在方法上加 synchronized 关键字，进行同步。最后，如果程序不是多线程的，那么使用 StringBuilder 效率高于 StringBuffer。 

### 5、String中的 ==

```java
String s1 = "helloworld";
String s2 = new String("helloworld");
String s3 = "hello";
String s4 = "world";
String s5 = "hello" + "world";
String s6 = s3 + s4;
System.out.println("s1==s2:" + (s1 == s2));
System.out.println("s1==s5:" + (s1 == s5));
System.out.println("s1==s6:" + (s1 == s6));
System.out.println("s1==s6.intern():" + (s1 == s6.intern()));
System.out.println("s2==s2.intern():" + (s2 == s2.intern()));
```

```java
s1==s2:false
s1==s5:true
s1==s6:false
s1==s6.intern():true
s2==s2.intern():false
```

### 6、Java 中的日期和时间

## 六、Java 的数据类型

### 1、基本数据类型及其占的字节数

| 四类   | 八种    | 字节数 | 描述                   |
| ------ | ------- | ------ | ---------------------- |
| 整型   | byte    | 1      | 8位（带符号位）        |
|        | short   | 2      | 16位（带符号位）       |
|        | int     | 4      | 32位（带符号位）       |
|        | long    | 8      | 64位（带符号位）       |
| 浮点型 | float   | 4      |                        |
|        | double  | 8      |                        |
| 字符型 | char    | 2      | 表示一个字符可以是中文 |
| 布尔型 | boolean | 1      | true,false             |

### 2、String是基本数据类型吗

String是引用数据类型，底层是char数组。

### 3、关于short 

```java
short s1 = 1;
s1 = s1 + 1;
```

1是int类型，s1 + 1结果也应该为int，需要强制类型转换才能赋给short。

```java
short s1 = 1;
s1 += 1;
```

+=隐含强制类型转换。

### 4、基本类型对应的包装类

| byte | short | int     | long | float | double | char      | boolean |
| ---- | ----- | ------- | ---- | ----- | ------ | --------- | ------- |
| Byte | Short | Integer | Long | Float | Double | Character | Boolean |

### 5、Integer 的比较

当数值范围在-128~127之间时直接引用常量池中的Integer对象。

### 6、String的常用方法

#### 1）length()

返回字符串长度

#### 2）indexOf(int ch)

查找ch字符在该字符串中第一次出现的位置

#### 3）indexOf(String str)

查找str子字符串在该字符串中第一次出现的位置

#### 4）lastIndexOf(int ch)

查找ch字符在该字符串中最后一次出现的位置

#### 5）indexOf(String str)

查找str子字符串在该字符串中最后一次出现的位置

#### 6）subString(int beginIndex)

获取从beginIndex位置开始到结束的子字符串

#### 7）subString(int beginIndex, int endIndex)

获取从beginIndex位置开始到endIndex位置的子字符串

#### 8）trim()

返回去除了前后空格的字符串

#### 9）equals(Object obj)

将该字符串与指定对象比较，返回true或false

#### 10）toLowerCase()

将字符串转换为小写

#### 11）toUpperCase()

将字符串转换为大写

#### 12）charAt(int index)

获取字符串中指定位置的字符

#### 13）split(String regex , int limit)

将字符串分割为子字符串，返回字符串数组

#### 14）getBytes()

将该字符串转换为byte数组

## 七、Java 的IO

### 1、java 中的流

#### 按流的方向

输入流(inputStream)和输出流(outputStream)。

#### 按处理数据的单位

字节流继承于InputStream和OutputStream。

字符流继承于InputStreamReader和OutputStreamWriter

### 2、字节流如何转为字符流

#### 输入流

InputStreamReader拥有构造函数可以传入InputStream对象。

#### 输出流

OutputStreamWriter拥有构造函数可以传入OutputStream对象。

### 3、将对象序列化到文件

创建对象

```java
public class Person implements Serializable {
    private Integer id;
    private String name;
    public Person(Integer id, String name) {
        this.id = id;
        this.name = name;
    }
    @Override
    public String toString() {
        return "Person{" +
                "id=" + id +
                ", name='" + name + '\'' +
                '}';
    }
    public Integer getId() {
        return id;
    }
    public void setId(Integer id) {
        this.id = id;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```

开始操作

```java
public class PersonTest {
    public static void main(String[] args) throws Exception {
        //写
        ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(new File("1.txt")));
        oos.writeObject(new Person(1,"张三"));
        oos.close();
        //读
        ObjectInputStream ois = new ObjectInputStream(new FileInputStream(new File("1.txt")));
        Person person = (Person) ois.readObject();
        System.out.println(person);
        ois.close();
    }
}
```

### 4、字节流和字符流的区别

#### 字节流

处理单元为一个字节，操作字节和字节数组；

以字节为单位，读到一个返回一个；

可以处理所有类型的数据：图片、MP3、AVI视频文件。

#### 字符流

处理的单元为2个字节的Unicode字符，分别为操作字符、字符数组或字符串；

使用字节流读到一个或多个字节(中文对应的字节数是两个，在UTF-8码表中是三个字节)时，先去查指定编码表，将查到的字符返回；

只能处理字符数据。

**处理纯文本优先使用字符流，除此之外都用字节流**

**在程序中一个字符等于两个字节**

### 5、通过序列化克隆对象

可以实现真正的深拷贝

### 6、什么是java序列化，如何实现java序列化

序列化是一种用来处理对象流的机制，对象流就是将对象的内容进行流化。可以对流化的对象进行读写操作，也可以将流化后的对象传输于网络之间。序列化是为了解决在对对象流进行读写操作时所引发的问题。

序列化的实现：将需要被序列化的类实现Serializable接口，该接口没有需要实现的方法，只是为了标注该对象是可被序列化的，然后使用一个输出流(如：FileOutputStream)来构造一个ObjectOutputStream(对象流)对象，接着使用ObjectOutputStream对象的writeObject(Object obj)方法就可以将参数为obj的对象写出(即保存其状态)，要恢复的话则用输入流。

原文链接：https://www.cnblogs.com/yangchunze/p/6728086.html

## 八、Java 的集合

### 1、HashMap 排序

```java
package com.lhq.hashmap;
import java.util.*;
public class SortHashMap {
    public static void main(String[] args) {
        HashMap<Integer, User> users = new HashMap<>();
        users.put(1,new User("张三",10));
        users.put(2,new User("李四",30));
        users.put(3,new User("王五",15));
        HashMap<Integer, User> sortHashMap = sortHashMap(users);
        System.out.println(sortHashMap);
    }
    public static HashMap<Integer,User> sortHashMap(HashMap<Integer,User> map){
        Set<Map.Entry<Integer, User>> entrySet = map.entrySet();
        List<Map.Entry<Integer, User>> list = new ArrayList<>(entrySet);
        Collections.sort(list, new Comparator<Map.Entry<Integer, User>>() {
            @Override
            public int compare(Map.Entry<Integer, User> o1, Map.Entry<Integer, User> o2) {
                return o2.getValue().getAge() - o1.getValue().getAge();
            }
        });
        LinkedHashMap<Integer, User> linkedHashMap = new LinkedHashMap<>();
        for (Map.Entry<Integer,User> entry:
             list) {
            linkedHashMap.put(entry.getKey(),entry.getValue());
        }
        return linkedHashMap;
    }
}
class User{
    private String name;
    private Integer age;

    public User(String name, Integer age) {
        this.name = name;
        this.age = age;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public Integer getAge() {
        return age;
    }
    public void setAge(Integer age) {
        this.age = age;
    }
    @Override
    public String toString() {
        return "User{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

### 2、集合安全性问题

在集合中 Vector 和 HashTable 把各自核心方法添加上了 synchronized 关键字，是线程安全的。

 ArrayList、HashSet、HashMap 每个方法都没有加锁，显然都是线程不安全的。

Collections 工具类提供了相关的 API，可以让上面那 3 个不安全的集合变为安全的。 

```java
Collections.synchronizedCollection(c);
Collections.synchronizedList(list);
Collections.synchronizedMap(m); 
```

上面几个函数都有对应的返回值类型，传入什么类型返回什么类型。

原理，就是将集合的核心方法添加上了 synchronized 关键字。 

### 3、ArrayList 内部用什么实现的？

内部是 Object[] 实现的。

### 4、并发集合和普通集合如何区别？

并发集合常见的有 ConcurrentHashMap、ConcurrentLinkedQueue、ConcurrentLinkedDeque 等。

并发集合位于 java.util.concurrent 包下，是 jdk1.5 之后才有的。

在 java 中有普通集合、同步（线程安全）的集合、并发集合。

普通集合通常性能最高，但是不保证多线程的安全性和并发的可靠性。

线程安全集合仅仅是给集合添加了 synchronized 同步锁，严重牺牲了性能，并且对并发的效率就更低了。

并发集合则通过复杂的策略不仅保证了多线程的安全又提高了并发时的效率。

### 5、List 的三个子类的特点

ArrayList 底层结构是数组，底层查询快，增删慢。

LinkedList 底层结构是链表型的，增删快，查询慢。

Vector 底层结构是数组线程安全的，增删慢，查询慢。

### 6、List 和 Map、Set 的区别

#### 6.1 结构特点

List 和 Set 是存储单列数据的集合，Map 是存储键和值这样的双列数据的集合；

List 中存储的数据是有顺序，并且允许重复；

Map 中存储的数据是没有顺序的，其键是不能重复的，它的值是可以重复的；

Set 中存储的数据是无序的，且不允许有重复，但元素在集合中的位置由元素的 hashcode 决定，位置是固定的（Set 集合根据 hashcode 来   82 进行数据的存储，所以位置是固定的，但是位置不是用户可以控制的，所以对于用户来说 set 中的元素还是无序的）。

#### 6.2 实现类

##### List 接口有三个实现类

LinkedList：基于链表实现，链表内存是散乱的，每一个元素存储本身内存地址的同时还存储下一个元素的地址。链表增删快，查找慢；

ArrayList：基于数组实现，非线程安全的，效率高，便于索引，但不 便于插入删除；

Vector：基于数组实现，线程安全的，效率低。

##### Map 接口有三个实现类

HashMap：基于 hash 表的 Map 接口实现，非线程安全，高效，支持 null 值和 null 键；

HashTable：线程安全，低效，不支持 null 值和 null 键；

LinkedHashMap：是 HashMap 的一个子类，保存了 记录的插入顺序；SortMap 接口：TreeMap，能够把它保存的记录根据键排序，默认是键值的升序排序。

#####  Set 接口有两个实现类

HashSet：底层是由 HashMap 实现，不允许集合中有重复的值，使用该方式时需要重 写 equals()和 hashCode()方法；

LinkedHashSet：继承与 HashSet，同时又基于 LinkedHashMap 来进行实现，底 层使用的是 LinkedHashMap。

#### 6.3 区别

List 集合中对象按照索引位置排序，可以有重复对象，允许按照对象在集合中的索引位置检索对象。

Map 中的每一个元素包含一个键和一个值，成对出现，键对象不可以重复，值对象可以重复。

Set 集合中的对象不按照特定的方式排序，并且没有重复对象，但它的实现类能对集合中的对象按照特定 的方式排序。

### 7、HashMap 和 HashTable 有什么区别？

HashMap 是线程不安全的，HashMap 是一个接口，是 Map 的一个子接口，是将键映射到值的对象，不允许键值重复，允许空键和空值；由于非线程安全，HashMap 的效率要较 HashTable 的效率高一些。

HashTable 是线程安全的一个集合，不允许 null 值作为一个 key 值或者 value 值。

HashTable 是 synchronized 多个线程访问时不需要自己为它的方法实现同步，而 HashMap 在被多个线程访问的时候需要为它的方法实现同步。

### 8、数组和链表分别比较适合用于什么场景，为什么？

#### 区别

##### 数组是将元素在内存中连续存储的；

###### 它的优点

因为数据是连续存储的，内存地址连续，所以在查找数据的时候效 率比较高

###### 它的缺点

在存储之前，我们需要申请一块连续的内存空间，并且在编译的时候就必须确定好它的空间的大 小。在运行的时候空间的大小是无法随着你的需要进行增加和减少而改变的，当数据两比较大的时候，有可能会出现 越界的情况，数据比较小的时候，又有可能会浪费掉内存空间。在改变数据个数时，增加、插入、删除数据效率比较低 

##### 链表是动态申请内存空间

不需要像数组需要提前申请好内存的大小，链表只需在用的时候申请就可以，根据需 要 来动态申请或者删除内存空间，对于数据增加和删除以及插入比数组灵活。

链表中数据在内存中可以在任意的位置，通过应用来关联数据（就是通过存在元素的指针来联系） 

#### 应用场景

##### 数组应用场景

数据比较少；经常做的运算是按序号访问数据元素；数组更容易实现，任何高级语言都支持；构建 的线性表较稳定。

##### 链表应用场景

对线性表的长度或者规模难以估计；频繁做插入删除操作；构建动态性比较强的线性表。

#### 面试题

用面向对象的方法求出数组中重复 value 的个数

```java
int[] arr = {1,4,1,4,2,5,4,5,8,7,8,77,88,5,4,9,6,2,4,1,5};
```

```java
int[] arr = {1,4,1,4,2,5,4,5,8,7,8,77,88,5,4,9,6,2,4,1,5};
HashMap<Integer, Integer> map = new HashMap<>();
for (int i:arr) {
    if (!map.containsKey(i)){
        map.put(i,1);
    } else {
        map.replace(i,map.get(i)+1);
    }
}
```



### 9、Java 中 ArrayList 和 LinkedList 区别？

ArrayList 和 Vector 使用了数组的实现，可以认为 ArrayList 或者 Vector 封装了对内部数组的操作，比如向数组中添加，删除，插入新的元素或者数据的扩展和重定向。

LinkedList 使用了循环双向链表。

**LinkedList 在添加和删除元素时具有比ArrayList更好的性能.但在get与set方面弱于ArrayList**

### 10、List a = new ArrayList() 和 ArrayList a =new ArrayList()的区别？

前者只能使用 List 的属性和方法，不能使用 ArrayList 特有的属性和方法，本质是一个 List 对象。

后者能使用 ArrayList 的方法和属性是一个 ArrayList 对象。

### 11、要对集合操作时，比较ArrayList 和 LinkedList 

当操作是在一列数据的后面添加数据而不是在前面或中间，并且需要随机地访问其中的元素时，使用 ArrayList 会提供比较好的性能；

当你的操作是在一列数据的前面或中间添加或删除数据，并且按照顺序访问其中的元素时，就应该使用 LinkedList 了。 

### 12、请用两个队列模拟堆栈结构。

```java
Queue<String> queue = new LinkedList<String>();
List<String> list = new LinkedList<String>();
queue.offer("a");
queue.offer("b");
queue.offer("c");
queue.offer("d");
queue.offer("e");
System.out.println("进栈");
for (String s : queue){
    System.out.println(s);
    list.add(s);
}
Queue<String> queue1 = new LinkedList<String>();
for (int i = list.size()-1;i>=0;i--){
    queue1.offer(list.get(i));
}
System.out.println("出栈");
for (String s : queue1){
    System.out.println(s);
}
```

```java
进栈:abcde
出栈:edcba
```

### 13、Collection 和 Map 的集成体系

![image-20201029165535050](C:\Users\13014\AppData\Roaming\Typora\typora-user-images\image-20201029165535050.png)

![image-20201029165557072](C:\Users\13014\AppData\Roaming\Typora\typora-user-images\image-20201029165557072.png)

### 14、Map 中的 key 和 value 可以为 null 么？

HashMap 允许 null 值 null 键。

HashTable 不允许 null 值 null 键。

key 均不能重复，若添加 key 相同的键值对，后面的 value 会自动覆盖前面的 value。

## 九、java 的多线程

### 1、程序、进程、线程基本概念

- 程序（program）：是为完成特定任务、用某种语言编写的一组指令的集合。即一段静态的代码，静态对象。

- 进程（progress）：程序的一次执行过程，或是正在运行的一个程序。是一个动态的过程：有它自身的产生、存在和消亡的过程。--生命周期

- - 程序是静态的，进程是动态的

  - 进程作为资源分配的单位，系统在运行时会为每个进程分配不同的内存区域。

  - 进程可以细化为多个线程

  - - 每个线程拥有自己独立的：栈、程序计数器。
    - 多个线程，共享同一个进程中的结构：方法区、堆。

- 线程（thread）：进程可进一步细化为线程，是一个程序内部的一条执行路径。

- - 若一个进程同一时间并行执行多个线程，就是支持多线程的。
  - 线程作为调度和执行的单位，每个线程拥有独立的运行栈和程序计数器（pc），线程切换的开销小。
  - 一个进程中多个线程共享相同的内存单元/内存地址空间->它们从同一堆中分配对象，可以访问相同的变量和对象。这就使得线程间通信更简便、高效。但多个线程操作共享的系统资源可能就会带来安全的隐患。

### 2、并行和并发

- 并行：多个CPU同时执行多个任务。比如：多个人同时做不同的事。
- 并发：一个CPU（采用时间片）"同时"执行多个任务。比如秒杀、多个人做同一件事。

### 3、多线程的优点

- 提高应用程序的响应。对图形界面更有意义，增强用户体验

- 提高CPU利用率

- 改善程序结构，将既长又复杂的进程分为多个线程，独立运行，利于理解和修改

- 何时需要多线程

- - 需要同时执行两个或多个任务
  - 需要实现等待的任务，如用户输入、文件读写、网络、搜索
  - 需要一些后台运行的程序时

### 4、线程的创建和使用

#### 1）传统使用类 Thread 和接口 Runnable 实现

##### 继承 Thread 类

```java
//方法一
class MyThread extends Thread{
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            if (i%2==0){
                System.out.println(Thread.currentThread().getName()+":"+i);
            }
        }
    }
}
public class ThreadTest{
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();
    }
}
//方法二
public class ThreadDemo {
    public static void main(String[] args) {
        //创建Thread类的匿名子类的方式
        new Thread(){
            @Override
            public void run() {
                for (int i = 0; i < 100; i++) {
                    if (i%2==0){
                        System.out.println(Thread.currentThread().getName()+":"+i);
                    }
                }
            }
        }.start();
        new Thread(){
            @Override
            public void run() {
                for (int i = 0; i < 100; i++) {
                    if (i%2!=0){
                        System.out.println(Thread.currentThread().getName()+":"+i);
                    }
                }
            }
        }.start();
    }
}
```

##### 实现 Runnable 接口

```java
//1.创建一个实现了Runnable接口的类
class MThread implements Runnable{
    //2.实现类去实现Runnable中的抽象方法
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            if (i%2==0){
                System.out.println(Thread.currentThread().getName()+":"+i);
            }
        }
    }
}
public class ThreadTest2 {
    public static void main(String[] args) {
        //3.创建实现类的对象
        MThread mThread = new MThread();
        //4.将此对象作为参数传递到Thread类的构造器中，创建Thread类的对象
        Thread t1 = new Thread(mThread);
        t1.setName("线程1");
        //5.通过Thread类的对象调用start（）:①启动线程；②调用当前线程的run（）-->调用Runnable类型的target
        t1.start();
        //再启动一个线程，遍历100以内的偶数
        Thread t2 = new Thread(mThread);
        t2.setName("线程2");
        t2.start();
    }
}
```

#### 2）JDK5.0新增线程创建方式

##### 实现 Callable 接口

```java
//1.创建一个实现Callable接口的实现类
class NumThread implements Callable{
    //2.实现call方法，将此线程需要执行的声明放到此线程中
    @Override
    public Object call() throws Exception {
        int sum = 0;
        for (int i = 1; i <= 100; i++) {
            if (i%2==0){
                sum+=i;
            }
        }
        return sum;
    }
}
public class ThreadNew {
    public static void main(String[] args) {
        //3.创建Callable接口实现类的对象
        NumThread numThread = new NumThread();
        //4.将此Callable接口实现类的对象，作为参数传递到FutureTask构造器中，创建FutureTask对象
        FutureTask futureTask = new FutureTask(numThread);
        //5.将FutureTask对象作为参数传递到Thread类的构造器中，创建Thread对象，并调用start（）
        new Thread(futureTask).start();
        try {
            //6.获取Callable中call方法的返回值
            //get方法的返回值即为FutureTask构造器参数Callable实现重写的call()的返回值
            Object o = futureTask.get();
            System.out.println(o);
        } catch (InterruptedException e) {
            e.printStackTrace();
        } catch (ExecutionException e) {
            e.printStackTrace();
        }
    }
}
```

###### 特点

- 与使用Runnable相比，Callable的功能更强大些

- - 相比run（）方法，可以有返回值
  - 方法可以抛出异常
  - 支持泛型返回值
  - 需要借助FutureTask类，比如获取返回结果

- Future接口

- - 可以对具体的Runnable、Callable任务的执行结果进行取消、查询是否完成、获取结果等。
  - FutureTask是Future接口的唯一实现类
  - FutureTask同时实现了Runnable，Future接口。既可以作为Runnable被线程执行，又可以作为Future得到Callable的返回值。

##### 使用线程池

```java
class NumberThread implements Runnable{
    @Override
    public void run() {

        for (int i = 1; i <=100 ; i++) {
            if (i%2==0){
                System.out.println(Thread.currentThread().getName()+i);
            }
        }
    }
}
class Number1Thread implements Runnable{
    @Override
    public void run() {

        for (int i = 1; i <=100 ; i++) {
            if (i%2!=0){
                System.out.println(Thread.currentThread().getName()+":"+i);
            }
        }
    }
}
public class ThreadPool {
    public static void main(String[] args) {
        //1.提供指定线程数量的线程池
        ExecutorService executorService = Executors.newFixedThreadPool(10);
        //设置线程池的属性
        ThreadPoolExecutor service = (ThreadPoolExecutor) executorService;
        service.setCorePoolSize(15);
        //        service.setKeepAliveTime();
        //2.执行指定的线程操作。需要提供实现Runnable接口或Callable接口实现类的对象
        executorService.execute(new NumberThread());//适合Runnable
        //        executorService.submit();//适合Callable
        executorService.execute(new Number1Thread());
        //        3.关闭连接池
        executorService.shutdown();
    }
}
```

###### 特点

- 提高了响应速度（减少创建新线程的时间）

- 降低资源消耗（重复利用线程池中的线程，不需要每次都创建）

- 便于线程管理

- - corePoolSize：核心池大小
  - maximumPoolSize：最大线程数
  - keepAliveTime：线程没有任务时最多保持多长时间后会终止。

## 十、Java 内部类

### 1、静态嵌套类（static nested class）和内部类（inner class）的不同

#### 静态嵌套类

Static Nested Class 是被声明为静态（static）的内部类，可以不依赖于外部类实例被实例化。

#### 内部类

需要在外部类实例化后才能实例化。

### 2、下面代码哪些地方会产生编译错误

```java
public class Outer {
    class Inner{}
    //错误
    /*public static void foo(){
        new Inner();
    }*/
    //无错误
    public void bar(){
        new Inner();
    }
    public static void main(String[] args) {
        //错误
        /*new Inner();*/
        //正确
        new Outer().new Inner();
    }
}
```



