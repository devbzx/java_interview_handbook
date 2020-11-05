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

