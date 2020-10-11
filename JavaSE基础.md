# JavaSE基础

## 面向对象

### 1、面向对象都有哪些特性

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

## JavaSE语法

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

## Java中的多态

### 1、java中实现多态的机制是什么

父类或接口定义的引用变量可以指向子类或具体实现类的实例对象，程序调用的方法在运行期才动态绑定，就是引用变量所指向的具体实例对象的方法，也就是内存里正在运行的那个对象的方法，而不是引用变量类型中定义的方法。

## Java的异常处理

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



