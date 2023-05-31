# Week7-Interface

# 方法接受一个示例作为参数的例子

```java
public class Person {
    private String name;
  
    public Person(String name) {
        this.name = name;
    }
  
    public String getName() {
        return name;
    }
}

public class Greeting {
    public static void sayHello(Person person) {
        String name = person.getName();
        System.out.println("Hello, " + name + "!");
    }
  
    public static void main(String[] args) {
        Person person = new Person("Alice");
        sayHello(person);
    }
}
```

在上面的例子中，`Greeting`​类中的`sayHello`​方法接受一个`Person`​类的对象作为参数。在`main`​方法中，我们创建了一个`Person`​对象，并将其作为参数传递给`sayHello`​方法。方法内部可以通过访问传入的`Person`​对象来执行相应的操作，这里是打印出问候语。

通过这种方式，我们可以在方法中操作不同的类对象，只要它们是方法所接受的参数类型或其子类。这样可以实现方法的通用性和灵活性。

‍

# 接口

在Java中，接口（Interface）是一种定义方法签名的抽象类型。它可以包含常量、抽象方法、默认方法和静态方法。接口定义了一组方法，但不提供方法的具体实现。其他类可以实现（implements）接口并提供方法的具体实现。

接口用于定义一组相关的操作或功能，它提供了一种规范，使得实现接口的类具有相同的行为。通过接口，可以实现多态性和代码的松耦合性。

下面是一个示例：

```java
// 定义一个接口
interface Drawable {
    void draw(); // 抽象方法，没有具体实现
}

// 实现接口的类
class Circle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Rectangle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a rectangle");
    }
}

// 使用接口
public class Main {
    public static void main(String[] args) {
        Drawable circle = new Circle();
        circle.draw(); // 调用实现类的方法

        Drawable rectangle = new Rectangle();
        rectangle.draw(); // 调用实现类的方法
    }
}
```

在上面的例子中，定义了一个`Drawable`​接口，它包含一个抽象方法`draw()`​。然后，`Circle`​和`Rectangle`​类分别实现了`Drawable`​接口，并提供了具体的`draw()`​方法的实现。在`Main`​类中，通过接口类型的引用，可以调用实现类的方法，实现了多态性的效果。

通过接口，可以定义一组共享的方法，让不同的类实现接口并提供自己的实现逻辑。这样可以达到代码重用和灵活性的目的，同时也提供了一种规范，使得不同的类具有相同的行为。

* Ishape接口

```java
public interface IShape {
public double getArea();
public double getPerimeter();
}
```

* Rectangle类

```java
public class Rectangle implements IShape {
private double width, height;
public Rectangle(double width, double height) {
this.width = width;
this.height = height;
} 
@Override
public double getArea() {
return width * height;
}
@Override
public double getPerimeter() {
return 2*width + 2*height;
}
}
```

* Circle类

```java
public class Circle implements IShape {
private double radius;
public Circle(double radius) {
this.radius = radius;
} 
@Override
public double getArea() {
return Math.PI * radius * radius;
}
@Override
public double getPerimeter() {
return 2 * Math.PI * radius;
}
}
```

* main程序

```java
public class Main {
public static void printShape( IShape ishape) { 
System.out.println("Area = " + ishape.getArea());
System.out.println("Perimeter = " + ishape.getPerimeter()); 
}
public static void main (String[] args) { 
//Rectangle rectangle = new Rectangle(20, 30);
Circle circle = new Circle(20);
printShape(circle); 
}
}
```

​`IShape ishape1 = new Rectangle(10,20);`​

​`IShape ishape2 = new Circle(20);`​

​`printShape(ishape1);`​

​`printShape(ishape2);`​

​`ArrayList<IShape> shapes = new ArrayList<>();`​​

```java
interface IA {…}
interface IB {…} 
class X implements IA {…} 
class Y implements IB {…} 
IA va; 
IB vb; 
X vx; 
Y vy
```

* ​`va = new X();`

该语句正确，X类实现了IA接口，可以将X的的实例赋值给接口类型的va

* ​`va = new IA();`

该语句错误，IA是接口，是抽象类型，不能被实例化

* ​`vx = new X();`​

整行代码为：`X vx=new X();`​，所以是合法的

* ​`vy = new X();`​

整行代码为：`Y vy=new X();`​，该语句非法，因为X和Y不是同一个类

* ​`va=vx`​

这是合法的，因为类 `X`​ 实现了接口 `IA`​，所以可以将 `X`​ 类型的变量 `vx`​ 赋值给接口类型的变量 `va`​

* `vy = new Y();`​

整行代码为`Y vy=new Y();`​，则是合法的，vy为Y类的实例

* ​`vb = new Y()`​

整行代码为`IB vb=new Y();`​，Y类实现了IB接口，因此可以将Y类的实例赋值给接口类型的vb

* ​`va = new Y();`​：非法
* ​`vb = new X();`​：非法
* ​`vb = vy;`​：合法

‍

‍

‍
