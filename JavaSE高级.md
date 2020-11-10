* [JavaSE高级](#javase%E9%AB%98%E7%BA%A7)
  * [一、java 中的反射](#%E4%B8%80java-%E4%B8%AD%E7%9A%84%E5%8F%8D%E5%B0%84)
  * [二、java 中的动态代理](#%E4%BA%8Cjava-%E4%B8%AD%E7%9A%84%E5%8A%A8%E6%80%81%E4%BB%A3%E7%90%86)
    * [1、写一个 ArrayList 的动态代理类](#1%E5%86%99%E4%B8%80%E4%B8%AA-arraylist-%E7%9A%84%E5%8A%A8%E6%80%81%E4%BB%A3%E7%90%86%E7%B1%BB)
    * [2、动静态代理的区别，什么场景使用？](#2%E5%8A%A8%E9%9D%99%E6%80%81%E4%BB%A3%E7%90%86%E7%9A%84%E5%8C%BA%E5%88%AB%E4%BB%80%E4%B9%88%E5%9C%BA%E6%99%AF%E4%BD%BF%E7%94%A8)
      * [静态代理](#%E9%9D%99%E6%80%81%E4%BB%A3%E7%90%86)
      * [动态代理](#%E5%8A%A8%E6%80%81%E4%BB%A3%E7%90%86)
  * [三、java 中的设计模式 &amp; 回收机制](#%E4%B8%89java-%E4%B8%AD%E7%9A%84%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F--%E5%9B%9E%E6%94%B6%E6%9C%BA%E5%88%B6)
    * [1、设计模式](#1%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F)
      * [1）创建型模式](#1%E5%88%9B%E5%BB%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F)
      * [2）结构型模式](#2%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F)
      * [3）行为型模式](#3%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F)
    * [2、单例模式](#2%E5%8D%95%E4%BE%8B%E6%A8%A1%E5%BC%8F)
      * [1）饿汉式](#1%E9%A5%BF%E6%B1%89%E5%BC%8F)
      * [2）懒汉式](#2%E6%87%92%E6%B1%89%E5%BC%8F)
    * [3、工厂设计模式](#3%E5%B7%A5%E5%8E%82%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F)
      * [1）普通工厂模式](#1%E6%99%AE%E9%80%9A%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F)
      * [2）多个工厂模式](#2%E5%A4%9A%E4%B8%AA%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F)
      * [3）静态工厂模式](#3%E9%9D%99%E6%80%81%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F)
      * [4）抽象工厂模式](#4%E6%8A%BD%E8%B1%A1%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F)
    * [4、建造者模式](#4%E5%BB%BA%E9%80%A0%E8%80%85%E6%A8%A1%E5%BC%8F)
    * [5、适配器设计模式](#5%E9%80%82%E9%85%8D%E5%99%A8%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F)
      * [1）类的适配器模式](#1%E7%B1%BB%E7%9A%84%E9%80%82%E9%85%8D%E5%99%A8%E6%A8%A1%E5%BC%8F)
      * [2）对象适配器模式](#2%E5%AF%B9%E8%B1%A1%E9%80%82%E9%85%8D%E5%99%A8%E6%A8%A1%E5%BC%8F)
      * [3）接口的适配器模式](#3%E6%8E%A5%E5%8F%A3%E7%9A%84%E9%80%82%E9%85%8D%E5%99%A8%E6%A8%A1%E5%BC%8F)
    * [6、装饰模式](#6%E8%A3%85%E9%A5%B0%E6%A8%A1%E5%BC%8F)
    * [7、策略模式](#7%E7%AD%96%E7%95%A5%E6%A8%A1%E5%BC%8F)
    * [8、观察者模式](#8%E8%A7%82%E5%AF%9F%E8%80%85%E6%A8%A1%E5%BC%8F)
    * [9、JVM 垃圾回收机制和常见算法](#9jvm-%E5%9E%83%E5%9C%BE%E5%9B%9E%E6%94%B6%E6%9C%BA%E5%88%B6%E5%92%8C%E5%B8%B8%E8%A7%81%E7%AE%97%E6%B3%95)
      * [1、定位无用对象的搜索算法](#1%E5%AE%9A%E4%BD%8D%E6%97%A0%E7%94%A8%E5%AF%B9%E8%B1%A1%E7%9A%84%E6%90%9C%E7%B4%A2%E7%AE%97%E6%B3%95)
        * [<del>1）引用计数器算法（废弃）</del>](#1%E5%BC%95%E7%94%A8%E8%AE%A1%E6%95%B0%E5%99%A8%E7%AE%97%E6%B3%95%E5%BA%9F%E5%BC%83)
        * [2）根搜索算法（使用）](#2%E6%A0%B9%E6%90%9C%E7%B4%A2%E7%AE%97%E6%B3%95%E4%BD%BF%E7%94%A8)
          * [GC Roots 对象包括](#gc-roots-%E5%AF%B9%E8%B1%A1%E5%8C%85%E6%8B%AC)
      * [2、回收算法如下](#2%E5%9B%9E%E6%94%B6%E7%AE%97%E6%B3%95%E5%A6%82%E4%B8%8B)
        * [1）标记 \- 清除算法（Mark \- Sweep）](#1%E6%A0%87%E8%AE%B0---%E6%B8%85%E9%99%A4%E7%AE%97%E6%B3%95mark---sweep)
          * [标记阶段](#%E6%A0%87%E8%AE%B0%E9%98%B6%E6%AE%B5)
          * [清除阶段](#%E6%B8%85%E9%99%A4%E9%98%B6%E6%AE%B5)
        * [2）复制算法（Copying）](#2%E5%A4%8D%E5%88%B6%E7%AE%97%E6%B3%95copying)
        * [3）标记整理算法（Mark \- Compact）](#3%E6%A0%87%E8%AE%B0%E6%95%B4%E7%90%86%E7%AE%97%E6%B3%95mark---compact)
        * [4）分代收集（Generational Collection）](#4%E5%88%86%E4%BB%A3%E6%94%B6%E9%9B%86generational-collection)
    * [10、谈谈 JVM 的内存结构](#10%E8%B0%88%E8%B0%88-jvm-%E7%9A%84%E5%86%85%E5%AD%98%E7%BB%93%E6%9E%84)
      * [1）强引用（StrongReference）](#1%E5%BC%BA%E5%BC%95%E7%94%A8strongreference)
      * [2）软引用（SoftReference）](#2%E8%BD%AF%E5%BC%95%E7%94%A8softreference)
      * [3）弱引用（WeakReference）](#3%E5%BC%B1%E5%BC%95%E7%94%A8weakreference)
      * [4）虚引用（PhantomReference）](#4%E8%99%9A%E5%BC%95%E7%94%A8phantomreference)
    * [12、heap 和 stack 有什么区别](#12heap-%E5%92%8C-stack-%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB)
      * [1）申请方式](#1%E7%94%B3%E8%AF%B7%E6%96%B9%E5%BC%8F)
        * [stack](#stack)
        * [heap](#heap)
      * [2）申请后系统的响应](#2%E7%94%B3%E8%AF%B7%E5%90%8E%E7%B3%BB%E7%BB%9F%E7%9A%84%E5%93%8D%E5%BA%94)
        * [stack](#stack-1)
        * [heap](#heap-1)
      * [3）申请大小的限制](#3%E7%94%B3%E8%AF%B7%E5%A4%A7%E5%B0%8F%E7%9A%84%E9%99%90%E5%88%B6)
        * [stack](#stack-2)
        * [heap](#heap-2)
      * [4）申请效率的比较](#4%E7%94%B3%E8%AF%B7%E6%95%88%E7%8E%87%E7%9A%84%E6%AF%94%E8%BE%83)
        * [stack](#stack-3)
        * [heap](#heap-3)
      * [5）heap 和 stack 中的存储内容](#5heap-%E5%92%8C-stack-%E4%B8%AD%E7%9A%84%E5%AD%98%E5%82%A8%E5%86%85%E5%AE%B9)
        * [stack](#stack-4)
        * [heap](#heap-4)
      * [6）数据结构层面](#6%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E5%B1%82%E9%9D%A2)
    * [13、解释内存中的栈（stack）、堆（heap）和方法区（method area）的用法](#13%E8%A7%A3%E9%87%8A%E5%86%85%E5%AD%98%E4%B8%AD%E7%9A%84%E6%A0%88stack%E5%A0%86heap%E5%92%8C%E6%96%B9%E6%B3%95%E5%8C%BAmethod-area%E7%9A%84%E7%94%A8%E6%B3%95)
  * [四、java 的类加载器](#%E5%9B%9Bjava-%E7%9A%84%E7%B1%BB%E5%8A%A0%E8%BD%BD%E5%99%A8)
    * [1、java 的类加载器的种类有哪些？](#1java-%E7%9A%84%E7%B1%BB%E5%8A%A0%E8%BD%BD%E5%99%A8%E7%9A%84%E7%A7%8D%E7%B1%BB%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [2、类什么时候被初始化？](#2%E7%B1%BB%E4%BB%80%E4%B9%88%E6%97%B6%E5%80%99%E8%A2%AB%E5%88%9D%E5%A7%8B%E5%8C%96)
      * [初始化步骤](#%E5%88%9D%E5%A7%8B%E5%8C%96%E6%AD%A5%E9%AA%A4)
    * [3、Java 类加载体系致 ClassLoader 双亲委托机制（待写）](#3java-%E7%B1%BB%E5%8A%A0%E8%BD%BD%E4%BD%93%E7%B3%BB%E8%87%B4-classloader-%E5%8F%8C%E4%BA%B2%E5%A7%94%E6%89%98%E6%9C%BA%E5%88%B6%E5%BE%85%E5%86%99)
    * [4、描述一下 JVM 加载 class](#4%E6%8F%8F%E8%BF%B0%E4%B8%80%E4%B8%8B-jvm-%E5%8A%A0%E8%BD%BD-class)
    * [5、获取一个类对象有哪些方式](#5%E8%8E%B7%E5%8F%96%E4%B8%80%E4%B8%AA%E7%B1%BB%E5%AF%B9%E8%B1%A1%E6%9C%89%E5%93%AA%E4%BA%9B%E6%96%B9%E5%BC%8F)
  * [五、JVM 基础知识](#%E4%BA%94jvm-%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86)
    * [1、既然有 GC 机制，为什么还有内存泄漏的情况？（待写）](#1%E6%97%A2%E7%84%B6%E6%9C%89-gc-%E6%9C%BA%E5%88%B6%E4%B8%BA%E4%BB%80%E4%B9%88%E8%BF%98%E6%9C%89%E5%86%85%E5%AD%98%E6%B3%84%E6%BC%8F%E7%9A%84%E6%83%85%E5%86%B5%E5%BE%85%E5%86%99)
  * [六、GC 基础知识](#%E5%85%ADgc-%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86)
    * [1、Java 中为什么会有 GC 机制](#1java-%E4%B8%AD%E4%B8%BA%E4%BB%80%E4%B9%88%E4%BC%9A%E6%9C%89-gc-%E6%9C%BA%E5%88%B6)
    * [2、对于 Java 的 GC 哪些内存需要回收](#2%E5%AF%B9%E4%BA%8E-java-%E7%9A%84-gc-%E5%93%AA%E4%BA%9B%E5%86%85%E5%AD%98%E9%9C%80%E8%A6%81%E5%9B%9E%E6%94%B6)
    * [3、Java 中的 GC 什么时候回收垃圾](#3java-%E4%B8%AD%E7%9A%84-gc-%E4%BB%80%E4%B9%88%E6%97%B6%E5%80%99%E5%9B%9E%E6%94%B6%E5%9E%83%E5%9C%BE)
  * [七、Java 8 的新特性以及使用（待写）](#%E4%B8%83java-8-%E7%9A%84%E6%96%B0%E7%89%B9%E6%80%A7%E4%BB%A5%E5%8F%8A%E4%BD%BF%E7%94%A8%E5%BE%85%E5%86%99)
  * [八、在开发中遇到过内存溢出么？原因有哪些？解决方法有哪些？](#%E5%85%AB%E5%9C%A8%E5%BC%80%E5%8F%91%E4%B8%AD%E9%81%87%E5%88%B0%E8%BF%87%E5%86%85%E5%AD%98%E6%BA%A2%E5%87%BA%E4%B9%88%E5%8E%9F%E5%9B%A0%E6%9C%89%E5%93%AA%E4%BA%9B%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95%E6%9C%89%E5%93%AA%E4%BA%9B)

# JavaSE高级

## 一、java 中的反射

java 中的反射首先是能够获取到 java 中要反射类的字节码，获取字节码有三种方法

1、Class.forName(classname) 

2、类名.class

3、this.getClass()

然后将字节码中的方法，变量，构造函数等映射成 相应的 Method、Filed、Constructor 等类，这些类提供了丰富的方法可以被我们所使用。 

## 二、java 中的动态代理

### 1、写一个 ArrayList 的动态代理类

```java
public class ArrayListProxy {
    public static void main(String[] args) {
        final List<String> list = new ArrayList<>();
        List<String> proxyInstance = 
                (List<String>) Proxy.newProxyInstance(
                        list.getClass().getClassLoader()
                        , list.getClass().getInterfaces()
                        , new InvocationHandler() {
                            @Override 
                            public Object invoke(Object proxy, Method method, Object[] args) throws Throwable { 
                                return method.invoke(list, args); 
                            }
                        });
        proxyInstance.add("你好");
        System.out.println(list);
    }
}
```

```java
"D:\Program Files\Java\jdk1.8.0_201\bin\java.exe" "-javaagent:D:\Program Files\JetBrains\IntelliJ IDEA 2020.2.1\lib\idea_rt.jar=55036:D:\Program Files\JetBrains\IntelliJ IDEA 2020.2.1\bin" -Dfile.encoding=UTF-8 -classpath "D:\Program Files\Java\jdk1.8.0_201\jre\lib\charsets.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\deploy.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\access-bridge-64.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\cldrdata.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\dnsns.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\jaccess.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\jfxrt.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\localedata.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\nashorn.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\sunec.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\sunjce_provider.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\sunmscapi.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\sunpkcs11.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\ext\zipfs.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\javaws.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\jce.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\jfr.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\jfxswt.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\jsse.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\management-agent.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\plugin.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\resources.jar;D:\Program Files\Java\jdk1.8.0_201\jre\lib\rt.jar;D:\code\java\javamdcode\out\production\javamdcode" com.lhq.java.ArrayListProxy
[你好]

Process finished with exit code 0
```

### 2、动静态代理的区别，什么场景使用？

#### 静态代理

静态代理通常只代理一个类，动态代理是代理一个接口下的多个实现类。

静态代理事先要知道代理的是什么。

#### 动态代理

动态代理不知道要代理什么东西，只有在运行时才知道。

动态代理是实现 JDK 里的 InvocationHandler 接口的 invoke 方法，但注意的是代理的是接口，也就是业务类必须要实现的接口，通过 Proxy 里的 newProxyinstance 得到代理的对象。

还有一种动态代理 CGLIB，代理的是类，不需要业务类继承接口，通过派生的子类来实现代理。通过在运行时，动态修改字节码达到修改类的目的。

AOP 编程时基于动态代理实现的。

## 三、java 中的设计模式 & 回收机制

### 1、设计模式

#### 1）创建型模式

- [x] 工厂方法模式
- [x] 抽象工厂模式
- [x] 单例模式
- [x] 建造者模式
- [ ] 原型模式

#### 2）结构型模式

- [x] 适配器模式
- [ ] 装饰器模式
- [x] 代理模式
- [ ] 外观模式
- [ ] 桥接模式
- [ ] 组合模式
- [x] 享元模式

#### 3）行为型模式

- [x] 策略模式
- [ ] 模板方法模式
- [x] 观察者模式
- [ ] 迭代子模式
- [ ] 责任链模式
- [ ] 命令模式
- [ ] 备忘录模 式
- [ ] 状态模式
- [ ] 访问者模式
- [ ] 中介者模式
- [ ] 解释器模式。

### 2、单例模式

#### 1）饿汉式

```java
//饿汉式,线程安全
class Bank{
    //私有化构造方法
    private Bank(){

    }
    //创建对象
    private static Bank instance = new Bank();
    //返回对象实例
    public static Bank getInstance(){
        return instance;
    }
}
```

#### 2）懒汉式

```java
class Ticket{
    //私有化构造方法
    private Ticket(){}
    //声明变量
    private static Ticket instance = null;
    //提供对外方法
    public static Ticket getInstance(){
        if (instance == null){
            synchronized (Ticket.class){
                if (instance == null){
                    instance = new Ticket();
                }
            }
        }
        return instance;
    }
}
```

### 3、工厂设计模式

Sender

```java
public interface Sender {
    public void Send();
}
```

MailSender

```java
public class MailSender implements Sender {
    @Override
    public void Send() {
        System.out.println("this is mail sender!");
    }
}
```

SmsSender

```java
public class SmsSender implements Sender {
    @Override
    public void Send() {
        System.out.println("this is sms sender");
    }
}
```



#### 1）普通工厂模式

建立一个工厂类，对实现了同一接口的一些类进行实例的创建。

SendFactory

```java
public class SendFactory {
    public Sender produce(String type){
        if ("mail".equals(type)){
            return new MailSender();
        } else if ("sms".equals(type)){
            return new SmsSender();
        } else {
            System.out.println("请输入正确的类型");
            return null;
        }
    }
}
```

#### 2）多个工厂模式

该模式是对普通工厂方法模式的改进，在普通工厂方法模式中，如果传递的字符串出错，则不能正确创建对象，而 多个工厂方法模式是提供多个工厂方法，分别创建对象。

SendFactory

```java
public class SendFactory {
    public Sender produceMail(){
        return new MailSender();
    }
    public Sender produceSms(){
        return new SmsSender();
    }
}
```

FactoryTest

```java
public class FactoryTest {
    public static void main(String[] args) {
        SendFactory factory = new SendFactory();
        Sender sender = factory.produceMail();
        sender.Send();
    }
}
```

#### 3）静态工厂模式

将上面的多个工厂方法模式里的方法置为静态的，不需要创建实例，直接调用即可。

SendFactory

```java
public class SendFactory {
    public static Sender produceMail(){
        return new MailSender();
    }
    public static Sender produceSms(){
        return new SmsSender();
    }
}
```

FactoryTest

```java
public class FactoryTest {
    public static void main(String[] args) {
        Sender sender = SendFactory.produceMail();
        sender.Send();
    }
}
```

#### 4）抽象工厂模式

工厂方法模式有一个问题就是，类的创建依赖工厂类，如果想要拓展程序，必须对工厂类进行修 改，这违背了闭包原则，所以，从设计角度考虑，有一定的问题，如何解决？就用到抽象工厂模式，创建多个工厂类，这样一旦需要增加新的功能，直接增加新的工厂类就可以了，不需要修改之前的代码。

增加 Provider 接口

```java
public interface Provider {
    public Sender produce();
}
```

SendMailFactory

```java
public class SendMailFactory implements Provider {
    @Override
    public Sender produce() {
        return new MailSender();
    }
}
```

SendSmsFactory

```java
public class SendSmsFactory implements Provider{
    @Override
    public Sender produce() {
        return new SmsSender();
    }
}
```

Test

```java
public class Test {
    public static void main(String[] args) {
        Provider provider = new SendMailFactory();
        Sender produce = provider.produce();
        produce.Send();
    }
}
```

### 4、建造者模式

工厂类模式提供的是单个类创建模式，而建造者模式则是将各种产品集中起来进行管理，用来创建复合对象，所谓复合对象就是指某个类具有不同的属性，其实建造者模式就是前面抽象工厂模式和最后的 Test 结合起来得到的。

Builder

```java
public class Builder {
    private List<Sender> list = new ArrayList<>();

    public void produceMailSender(int count){
        for (int i = 0; i < count; i++) {
            list.add(new MailSender());
        }
    }

    public void produceSmsSender(int count){
        for (int i = 0; i < count; i++) {
            list.add(new SmsSender());
        }
    }
}
```

TestBuilder

```java
public class TestBuilder {
    public static void main(String[] args) {
        Builder builder = new Builder();
        builder.produceMailSender(10);
    }
}
```

### 5、适配器设计模式

适配器模式将某个类的接口转换成客户端期望的另一个接口表示，目的是消除由于接口不匹配所造成的类的兼容性问题。主要分为三类：类的适配器模式、对象的适配器模式、接口的适配器模式。

#### 1）类的适配器模式

 Souce

```java
public class Source {
    public void method1(){
        System.out.println("this is original method");
    }
}
```

Adapter

```java
public class Adapter extends Source implements Targetable {
    @Override
    public void method2() {
        System.out.println("this is the targetable method");
    }
}
```

Targetable 接口

```java
public interface Targetable {
    //与原类中的方法相同
    public void method1();
    //新类的方法
    public void method2();

}
```

AdapterTest

```java
public class AdapterTest {
    public static void main(String[] args) {
        Targetable target = new Adapter();
        target.method1();
        target.method2();
    }
}
```

#### 2）对象适配器模式

基本思路和类的适配器模式相同，只是将 Adapter 类作修改，这次不继承 Source 类，而是持有 Source 类的实例，以达到解决兼容性的问题。

Source、Targetable 与类的适配器模式的 Source、Targetable 相同

Wrapper

```java
public class Wrapper implements Targetable {
    private Source source;

    public Wrapper(Source source) {
        super();
        this.source = source;
    }

    @Override
    public void method1() {
        source.method1();
    }

    @Override
    public void method2() {
        System.out.println("this is the targetable method");
    }
}
```

AdapterTest

```java
public class AdapterTest {
    public static void main(String[] args) {
        Source source = new Source();
        Targetable target = new Wrapper(source);
        target.method1();
        target.method2();
    }
}
```

#### 3）接口的适配器模式

一个接口中有多个抽象方法，实现该接口，必须实现该接口的所有方法，借助于一个抽象类，该抽象类实现了该接口，实现了所有的方法，我们写一个类，继承该抽象类，重写我们需要的方法。

Animal 接口

```java
public interface Animal {
    void eat();
    void run();
    void sleep();
}
```

AnimalAdapter

```java
public abstract class AnimalAdapter implements Animal {

    @Override
    public void eat() {

    }

    @Override
    public void run() {

    }

    @Override
    public void sleep() {

    }
}
```

Dog

```java
public class Dog extends AnimalAdapter {
    @Override
    public void eat() {
        System.out.println("汪汪汪，真香");
    }
}
```

### 6、装饰模式

动态给一个对象增加一些新的功能

要求装饰对象和被装饰对象实现同一个 接口，装饰对象持有被装饰对象的实例。 

Sourceable 接口

```java
public interface Sourceable {
    public void method();
}
```

Source

```java
public class Source implements Sourceable {
    @Override
    public void method() {
        System.out.println("the original method!");
    }
}
```

Decorator

```java
public class Decorator implements Sourceable {
    private Sourceable source;

    public Decorator(Sourceable source) {
        super();
        this.source = source;
    }

    @Override
    public void method() {
        System.out.println("before decorator");
        source.method();
        System.out.println("after decorator");
    }
}
```

DecoratorTest

```java
public class DecoratorTest {
    public static void main(String[] args) {
        Sourceable source = new Source();
        Sourceable obj = new Decorator(source);
        obj.method();
    }
}
```

### 7、策略模式

策略模式定义了一系列算法，并将每个算法封装起来，使他们可以相互替换，且算法的变化不会影响到使用算法的客户。需要设计一个接口，为一系列实现类提供统一的方法，多个实现类实现该接口，设计一个抽象类（可有可无，属于辅助类），提供辅助函数。策略模式的决定权在用户，系统本身提供不同算法的实现，新增或者删除算法，对各种算法做封装。因此，策略模式多用在算法决策系统中，外部用户只需要决定用哪个算法即可。

ICalculator 接口

```java
public interface ICalculator {
    public int calculate(String exp);
}
```

AbstractCalculator

```java
public class AbstractCalculator {
    public int[] split(String exp,String opt){
        String[] array = exp.split(opt);
        int[] arrayInt = new int[2];
        arrayInt[0] = Integer.parseInt(array[0]);
        arrayInt[1] = Integer.parseInt(array[1]);
        return arrayInt;
    }
}
```

Minus

```java
public class Minus extends AbstractCalculator implements ICalculator {
    @Override
    public int calculate(String exp) {
        int[] arrayInt = split(exp, "-");
        return arrayInt[0]-arrayInt[1];
    }
}
```

Plus

```java
public class Plus extends AbstractCalculator implements ICalculator {
    @Override
    public int calculate(String exp) {
        int[] arrayInt = split(exp, "\\+");
        return arrayInt[0]+arrayInt[1];
    }
}
```

StrategyTest

```java
public class StrategyTest {
    public static void main(String[] args) {
        String exp = "2+8";
        ICalculator cal = new Plus();
        int result = cal.calculate(exp);
        System.out.println(result);
    }
}
```

### 8、观察者模式

当一个对象变化时，其 它依赖该对象的对象都会收到通知，并且随着变化！对象之间是一种一对多的关系。 

Observer 接口

```java
public interface Observer {
    public void update();
}
```

Subject 接口

```java
public interface Subject {
    //增加观察者
    public void add(Observer observer);
    //删除观察者
    public void del(Observer observer);
    //通知所有观察者
    public void notifyObservers();
    //自身操作
    public void operation();
}
```

AbstractSubject

```java
public class AbstractSubject implements Subject {
    private Vector<Observer> vector = new Vector<Observer>();
    @Override
    public void add(Observer observer) {
        vector.add(observer);
    }

    @Override
    public void del(Observer observer) {
        vector.remove(observer);
    }

    @Override
    public void notifyObservers() {
        Enumeration<Observer> enumo = vector.elements();
        while (enumo.hasMoreElements()){
            enumo.nextElement().update();
        }
    }

    @Override
    public void operation() {

    }
}
```

Observer1 

```java
public class Observer1 implements Observer {
    @Override
    public void update() {
        System.out.println("observer1 has received");
    }
}
```

Observer2

```java
public class Observer2 implements Observer {
    @Override
    public void update() {
        System.out.println("observer2 has received");
    }
}
```

MySubject

```java
public class MySubject extends AbstractSubject {
    @Override
    public void operation() {
        System.out.println("update self");
        notifyObservers();
    }
}
```

ObserverTest

```java
public class ObserverTest {
    public static void main(String[] args) {
        Subject sub = new MySubject();
        sub.add(new Observer1());
        sub.add(new Observer2());
        sub.operation();
    }
}
```

### 9、JVM 垃圾回收机制和常见算法

GC（Garbage Collector）在回收对象前首先必须发现那些无用对象

#### 1、定位无用对象的搜索算法

##### ~~1）引用计数器算法（废弃）~~

给每个对象设置一个计数器，当有地方引用这个对象的时候，计数器 +1，当引用失效的时候，计数器 -1，当计数器为 0 的时候，成为垃圾。

引用计数器实现简单，效率高；但是不能解决循环依赖问题（A 对象引用 B 对象，B 对象又引用 A 对象，但是 A,B 对象已不被任何其他对象引用），同时每次计数器的增加和较少都带来了很多额外的开销，所以 JDK 1.1 以后这个算法就不再使用了。

##### 2）根搜索算法（使用）

根搜索算法是通过一些“GC Roots”对象作为起点，从这些节点开始往下搜索，搜索**通过的路径成为引用链** （Reference Chain），当一个对象**没有被 GC Roots 的引用链连接的时候**，说明这个对象是**不可用**的。 

###### GC Roots 对象包括

a) 虚拟机栈（栈帧中的本地变量表）中的引用的对象。 

b) 方法区域中的类静态属性引用的对象。 

c) 方法区域中常量引用的对象。 

d) 本地方法栈中 JNI（Native 方法）的引用的对象。 

通过上面的算法搜索到无用对象之后，就是回收过程，

#### 2、回收算法如下

##### 1）标记 - 清除算法（Mark - Sweep）

（DVM 使用的算法）

分为两个阶段："标记" 和 "清除"。

###### 标记阶段

确定要回收的对象，并做标记

###### 清除阶段

紧随标记阶段，将标记阶段确定不可用的对象清除。

标记—清除算法是基础的收集算法，标记和清除阶段的效率不高， 而且清除后回产生大量的不连续空间，这样当程序需要分配大内存对象时，可能无法找到足够的连续空间。

##### 2）复制算法（Copying）

复制算法是把**内存分成大小相等的两块**，每次使用其中一块，当垃圾回收的时候，**把存活的对象复制到另一块上**， 然后把这块内存整个清理掉。

复制算法实现简单，运行效率高，但是由于每次只能使用其中的一半，造成内存的利用率不高。

现在的 JVM 用复制方法收集新生代，由于新生代中大部分对象（98%）都是朝生夕死的，所以两块内存的比例 不是 1:1(大概是 8:1)。 

##### 3）标记整理算法（Mark - Compact）

标记—整理算法和标记—清除算法一样，但是标记—整理算法不是把存活对象复制到另一块内存，而是**把存活对象往内存的一端移动**，然后**直接回收边界以外的内存**。

标记—整理算法提高了内存的利用率，并且它**适合在收集对象存活时间较长的老年代**。 

##### 4）分代收集（Generational Collection）

分代收集是根据对象的存活时间把内存分为新生代和老年代，根据各个代对象的存活特点，每个代采用不同的垃圾回收算法。

新生代采用复制算法，

老年代采用标记—整理算法。

垃圾算法的实现涉及大量的程序细节，而且不同的虚拟机平台实现的方法也各不相同。 

### 10、谈谈 JVM 的内存结构

Java 中对象的引用分为四种级别，这四种级别由高到低依次为：**强引用、软引用、弱引用和虚引用**。

#### 1）强引用（StrongReference）

```java
String abc=new String("abc");
```

如果一个对象被被人拥有**强引用**，那么垃圾回收器**绝不会回收它**。当内存空间不足，Java 虚拟机宁愿抛出 OutOfMemoryError 错误，使程序异常终止，也不会靠随意回收具有强引用的对象来解决内存不足问题。

Java 的对象是位于 heap 中的，heap 中对象有**强可及对象**、**软可及对象**、**弱可及对象**、**虚可及对象**和**不可到达对象**。应用的强弱顺序是强、软、弱、和虚。对于对象是属于哪种可及的对象，由他的最强的引用决定。

```java
String abc=new String("abc"); //1
SoftReference<String> softRef=new SoftReference<String>(abc); //2
WeakReference<String> weakRef = new WeakReference<String>(abc); //3
abc=null; //4
softRef.clear();//5 
```

第一行在 heap 堆中创建内容为“abc”的对象，并建立 abc 到该对象的强引用，该对象是强可及的。 

第二行和第三行分别建立对 heap 中对象的软引用和弱引用，此时 heap 中的 abc 对象已经有 3 个引用，显然此 时 abc 对象仍是强可及的。

第四行之后 heap 中对象不再是强可及的，变成软可及的。

第五行执行之后变成弱可及的。

#### 2）软引用（SoftReference）

如果一个对象只具有软引用，那么如果**内存空间足够**，垃圾回收器就**不会回收它**， 如果**内存空间不足**了，就会**回收这些对象的内存**。只要垃圾回收器没有回收它，该对象就可以被程序使用。软引用可用来实现内存敏感的高速缓存。

软引用可以和一个引用队列（ReferenceQueue）联合使用，如果软引用所引用的对象被垃圾回收，Java 虚拟机就会把这个软引用加入到与之关联的引用队列中。 

软引用是主要用于内存敏感的高速缓存。

在 jvm 报告内存不足之前会清除所有的软引用，这样以来 gc 就有 可能收集软可及的对象，可能解决内存吃紧问题，避免内存溢出。什么时候会被收集取决于 gc 的算法和 gc 运行 时可用内存的大小。

#### 3）弱引用（WeakReference）

如果一个对象只具有弱引用，那该类就是可有可无的对象，因为只要该对象被 gc 扫描到了随时都会把它干掉。

弱引用与软引用的区别在于：只具有弱引用的对象拥有更短暂的生命周期。

在垃圾回收器线程扫描它所管辖的内存区域的过程中，一旦发现了只具有弱引用的对象，不管当前内存空间足够与否，都会回收它的内存。不过，由于垃圾回收器是一个优先级很低的线程，因此不一定会很快发现那些只具有弱引用的对象。

弱引用可以和一个引用队列（ReferenceQueue）联合使用，如果弱引用所引用的对象被垃圾回收，Java 虚 拟机就会把这个弱引用加入到与之关联的引用队列中。 

#### 4）虚引用（PhantomReference） 

"虚引用"顾名思义，就是形同虚设，与其他几种引用都不同，虚引用并不会决定对象的生命周期。

如果一个对象仅持有虚引用，那么它就和没有任何引用一样，在任何时候都可能被垃圾回收。虚引用主要用来跟踪对象被垃圾回收的活动。

虚引用与软引用和弱引用的一个区别在于：虚引用必须和引用队列（ReferenceQueue）联合使用。

当垃圾回收器准备回收一个对象时，如果发现它还有虚引用，就会在回收对象的内存之前，把这个虚 引用加入到与之关联的引用队列中。

程序可以通过判断引用队列中是否已经加入了虚引用，来了解被引用的对象是否将要被垃圾回收。

程序如果发现某个虚引用已经被加入到引用队列，那么就可以在所引用的对象的内存被回收之前采取必要的行动。 

建立虚引用之后通过 get 方法返回结果始终为 null,通过源代码你会发现,虚引用通向会把引用的对象写进 referent,只是 get 方法返回结果为 null。先看一下和 gc 交互的过程再说一下他的作用。

1 不把 referent 设置为 null, 直接把 heap 中的 new String("abc")对象设置为可结束的(finalizable)。 

2 与软引用和弱引用不同, 先把 PhantomRefrence 对象添加到它的 ReferenceQueue 中.然后在释放虚可及的对象。

### 12、heap 和 stack 有什么区别

#### 1）申请方式

##### stack

由系统自动分配。例如，声明在函数中一个局部变量 int b; 系统自动在栈中为 b 开辟空间 

##### heap

需要程序员自己申请，并指明大小，在 c 中 malloc 函数，对于 Java 需要手动 new Object()的形式开辟 

#### 2）申请后系统的响应 

##### stack

只要栈的剩余空间大于所申请空间，系统将为程序提供内存，否则将报异常提示栈溢出。

##### heap

首先应该知道操作系统有一个记录空闲内存地址的链表，当系统收到程序的申请时， 会遍历该链表，寻找第一个空间大于所申请空间的堆结点，然后将该结点从空闲结点链表中删除，并将该结点的空 间 分配给程序。另外，由于找到的堆结点的大小不一定正好等于申请的大小，系统会自动的将多余的那部分重新放入空闲链表中。

#### 3）申请大小的限制

##### stack

栈是向低地址扩展的数据结构，是一块连续的内存的区域。这句话的意思是栈顶的地址和栈的最大容量是 系统预先规定好的，在 WINDOWS 下，栈的大小是 2M（也有的说是 1M，总之是一个编译时就确定的常数），如果 申请的空间超过栈的剩余空间时，将提示 overflow。因此，能从栈获得的空间较小。 

##### heap

堆是向高地址扩展的数据结构，是不连续的内存区域。这是由于系统是用链表来存储的空闲内存地址的， 自然是不连续的，而链表的遍历方向是由低地址向高地址。堆的大小受限于计算机系统中有效的虚拟内存。由此可见， 堆获得的空间比较灵活，也比较大。 

#### 4）申请效率的比较

##### stack

由系统自动分配，速度较快。但程序员是无法控制的。

##### heap

由 new 分配的内存，一般速度比较慢，而且容易产生内存碎片,不过用起来最方便。

#### 5）heap 和 stack 中的存储内容

##### stack

 在函数调用时，第一个进栈的是主函数中后的下一条指令（函数调用语句的下一条可执行语句）的地址， 然后是函数的各个参数，在大多数的 C 编译器中，参数是由右往左入栈的，然后是函数中的局部变量。注意静态变量 是不入栈的。 

当本次函数调用结束后，局部变量先出栈，然后是参数，最后栈顶指针指向最开始存的地址，也就是主函数中的下 一条指令，程序由该点继续运行。 

##### heap

一般是在堆的头部用一个字节存放堆的大小。堆中的具体内容有程序员安排。

#### 6）数据结构层面

这里的堆实际上指的就是（满足堆性质的）优先队列的一 种数据结构，第 1 个元素有最高的优先权；

栈实际上就是满足先进后出的性质的数学或数据结构。 

虽然堆栈，堆栈的说法是连起来叫，但是他们还是有很大区别的，连着叫只是由于历史的原因。 

### 13、解释内存中的栈（stack）、堆（heap）和方法区（method area）的用法

通常我们**定义一个基本数据类型的变量，一个对象的引用**，还有就是**函数调用的现场保存**都使用 JVM 中的**栈空间**；

而通过 **new 关键字和构造器创建的对象**则放在**堆空间**，堆是垃圾收集器管理的主要区域，由于现在的垃圾收集器 都采用分代收集算法，所以堆空间还可以细分为新生代和老生代，再具体一点可以分为 Eden、Survivor（又可分为 From Survivor 和 To Survivor）、Tenured；

方法区和堆都是各个线程共享的内存区域，用于存储已经被 JVM 加载 的类信息、常量、静态变量、JIT 编译器编译后的代码等数据；

程序中的**字面量**（literal）如**直接书写的 100、"hello" 和常量**都是放在**常量池**中，**常量池是方法区的一部分**。

栈空间操作起来最快但是栈很小，通常大量的对象都是放在堆空间，栈和堆的大小都可以通过 JVM 的启动参数来进行调整，栈空间用光了会引发 StackOverflowError，而堆和常量池空间不足则会引发 OutOfMemoryError。

```java
String str = new String("hello"); 
```

上面的语句中变量 str 放在栈上，用 new 创建出来的字符串对象放在堆上，而"hello"这个字面量是放在方法区的。 

## 四、java 的类加载器

### 1、java 的类加载器的种类有哪些？

1）根类加载器（BootStrap）

2）扩展类加载器（Extension） ---加载位置：jre\lib\ext 中

3）系统（应用）类加载器（System\App） ---加载位置：classpath 中

4）自定义加载器（必须继承 ClassLoader）

### 2、类什么时候被初始化？

1）创建类的实例，也就是 new 一个对象 

2）访问某个类或接口的静态变量，或者对该静态变量赋值 

3）调用类的静态方法 

4）反射（Class.forName("com.lyj.load")） 

5）初始化一个类的子类（会首先初始化子类的父类） 

6）JVM 启动时标明的启动类，即文件名和类名相同的那个类 

只有 这 6 中情况才会导致类的类的初始化

#### 初始化步骤

1）如果这个类还没有被加载和链接，那先进行加载和链接 

2）假如这个类存在直接父类，并且这个类还没有被初始化（注意：在一个类加载器中，类只能初始化一 次），那就初始化直接的父类（不适用于接口） 

3）加入类中存在初始化语句（如 static 变量和 static 块），那就依次执行这些初始化语句。 

### 3、Java 类加载体系致 ClassLoader 双亲委托机制（待写）

### 4、描述一下 JVM 加载 class

JVM 中类的装载是由类加载器（ClassLoader）和它的子类来实现的，Java 中的类加载器是一个重要的 Java 运 行时系统组件，它负责在运行时查找和装入类文件中的类。 

由于 Java 的跨平台性，经过编译的 Java 源程序并不是一个可执行程序，而是一个或多个类文件。

当 Java 程序 需要使用某个类时,JVM 会确保这个类已经被加载、连接（验证、准备和解析）和初始化。

类的加载是指把类的.class 文件中的数据读入到内存中，通常是创建一个字节数组读入.class 文件，然后产生与所加载类对应的 Class 对象。

加载完成后，Class 对象还不完整，所以此时的类还不可用。

当类被加载后就进入连接阶段，这一阶段包括验证、准备 （为静态变量分配内存并设置默认的初始值）和解析（将符号引用替换为直接引用）三个步骤。

最后 JVM 对类进行初始化，包括：如果类存在直接的父类并且这个类还没有被初始化，那么就先初始化父类； 如果类中存在初始化语句，就依次执行这些初始化语句。

类的加载是由类加载器完成的，类加载器包括：根加载器 （BootStrap）、扩展加载器（Extension）、系统加载器（System）和用户自定义类加载器（java.lang.ClassLoader 的子类）。

从 Java 2（JDK 1.2）开始，类加载过程采取了父亲委托机制（PDM）。

PDM 更好的保证了 Java 平台的安全性，在该机制中，JVM 自带的 Bootstrap 是根加载器，其他的加载器都有且仅有一个父类加载器。

类的加载首先请求 父类加载器加载，父类加载器无能为力时才由其子类加载器自行加载。

JVM 不会向 Java 程序提供对 Bootstrap 的引用。 

**下面是关于几个类加载器的说明：**

 • Bootstrap：一般用本地代码实现，负责加载 JVM 基础核心类库（rt.jar）；

 • Extension：从 java.ext.dirs 系统属性所指定的目录中加载类库，它的父加载器是 Bootstrap； 

• System：又叫应用类加载器，其父类是 Extension。它是应用最广泛的类加载器。它从环境变量 classpath 或者系统属性 java.class.path 所指定的目录中记载类，是用户自定义加载器的默认父加载器。 

### 5、获取一个类对象有哪些方式

类型.class

例如：

```java 
String.class 
```

对象.getClass()

例如：

```java 
"hello".getClass() 
```

Class.forName()

例如： 

```java
Class.forName("java.lang.String") 
```

## 五、JVM 基础知识

### 1、既然有 GC 机制，为什么还有内存泄漏的情况？（待写）

## 六、GC 基础知识 

### 1、Java 中为什么会有 GC 机制

 安全性考虑；-- for security.

 减少内存泄露；-- erase memory leak in some degree. 

 减少程序员工作量。-- Programmers don't worry about memory releasing. 

### 2、对于 Java 的 GC 哪些内存需要回收

GC 主要进行回收的内存是 JVM 中的方法区和堆

### 3、Java 中的 GC 什么时候回收垃圾

可达性分析(Reachability Analysis)。

 所有生成 的对象都是一个称为"GC Roots"的根的子树。

从 GC Roots 开始向下搜索，搜索所经过的路径称为引用链 (Reference Chain)，当一个对象到 GC Roots 没有任何引用链可以到达时，就称这个对象是不可达的（不可引用的）， 也就是可以被 GC 回收了。 

## 七、Java 8 的新特性以及使用（待写）

## 八、在开发中遇到过内存溢出么？原因有哪些？解决方法有哪些？

**引起内存溢出的原因有很多种，常见的有以下几种**

1.内存中加载的数据量过于庞大，如一次从数据库取出过多数据； 2.集合类中有对对象的引用，使用完后未清空，使得 JVM 不能回收； 

3.代码中存在死循环或循环产生过多重复的对象实体； 

4.使用的第三方软件中的 BUG； 

5.启动参数内存值设定的过小； 

**内存溢出的解决方案** 

**第一步**，修改 JVM 启动参数，直接增加内存。(-Xms，-Xmx 参数一定不要忘记加。) 

**第二步**，检查错误日志，查看“OutOfMemory”错误前是否有其它异常或错误。 

**第三步**，对代码进行走查和分析，找出可能发生内存溢出的位置。 

**重点排查以下几点** 

1.检查对数据库查询中，是否有一次获得全部数据的查询。一般来说，如果一次取十万条记录到内存，就可能 引起内存溢出。这个问题比较隐蔽，在上线前，数据库中数据较少，不容易出问题，上线后，数据库中数据多了，一次 查询就有可能引起内存溢出。因此对于数据库查询尽量采用分页的方式查询。 

2.检查代码中是否有死循环或递归调用。 

3.检查是否有大循环重复产生新对象实体。 

4.检查对数据库查询中，是否有一次获得全部数据的查询。一般来说，如果一次取十万条记录到内存，就可能 引起内存溢出。这个问题比较隐蔽，在上线前，数据库中 数据较少，不容易出问题，上线后，数据库中数据多了， 一次查询就有可能引起内存溢出。因此对于数据库查询尽量采用分页的方式查询。 

5.检查 List、MAP 等集合对象是否有使用完后，未清除的问题。List、MAP 等集合对象会始终存有对对象的 引用，使得这些对象不能被 GC 回收。

**第四步**，使用内存查看工具动态查看内存使用情况。 

