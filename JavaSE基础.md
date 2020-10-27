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

