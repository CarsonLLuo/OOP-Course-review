# Week6-Inheritance

# extend, super,this关键字

1. extend

是用来表示继承关系的关键字。在Java中，类可以继承另一个类的属性和方法，通过使用extends关键字可以创建一个新类，该类继承了父类的属性和方法。

```java
// 定义一个父类
class Animal {
  public void makeSound() {
    System.out.println("Animal is making a sound.");
  }
}

// 定义一个继承自Animal的子类
class Dog extends Animal {
  public void makeSound() {
    System.out.println("Dog is barking.");
  }
}

// 创建一个Dog实例并调用makeSound方法
Dog dog = new Dog();
dog.makeSound(); // 输出：Dog is barking.

```

A class may have one, many or no subclasses.一个类可以有一个，多个或者没有子类

A class may have only one superclass.一个类只能有一个父类，没有多重继承

在Java中，一个类只能直接继承自一个父类，这被称为单继承。也就是说，一个类只能有一个直接父类。

这种单继承的限制是为了保持继承关系的清晰和简单，避免出现复杂的继承链和潜在的冲突。通过单继承，每个类都有一个明确的父类，可以更好地组织和扩展代码。

然而，Java 提供了一种间接实现多继承特性的机制，即通过接口（Interface）。一个类可以实现多个接口，从而获得多个父类接口的功能。

2. supper

是用来表示调用父类方法或构造函数的关键字。在Java中，子类可以使用super关键字来调用父类的构造函数或者父类中被覆盖的方法。

```java
// 定义一个父类
class Animal {
  public Animal(String name) {
    System.out.println("Animal's name is " + name);//父类构造函数
  }
}

// 定义一个继承自Animal的子类
class Dog extends Animal {
  public Dog(String name) {
    super(name); // 调用父类的构造函数
    System.out.println("Dog's name is " + name);
  }
}

// 创建一个Dog实例并输出其名字
Dog dog = new Dog("Buddy");
// 输出：
// Animal's name is Buddy
// Dog's name is Buddy
```

3. this

是用来表示当前对象的引用的关键字。在Java中，this关键字可以用来引用当前对象的属性和方法，也可以用来调用当前类的构造函数。

```java
class Person {
  private String name;
  private int age;

  public Person(String name, int age) {
    this.name = name; // 使用this关键字引用当前对象的name属性
    this.age = age; // 使用this关键字引用当前对象的age属性
  }

  public void printInfo() {
    System.out.println("Name: " + this.name + ", Age: " + this.age); // 使用this关键字引用当前对象的属性
  }
}

// 创建一个Person实例并输出其信息
Person person = new Person("John", 25);
person.printInfo(); // 输出：Name: John, Age: 25

```

‍

# Inheritance继承

继承（Inheritance）是面向对象编程中的一个重要概念，它允许一个类（称为子类或派生类）继承另一个类（称为父类或基类）的属性和方法。通过继承，子类可以重用父类的代码，并在此基础上添加新的属性和方法，从而形成类之间的层次结构。

继承的关系中，父类拥有通用的特性和行为，而子类可以具有更具体和特殊化的特性和行为。子类可以访问父类的非私有成员（如属性和方法），并且可以覆盖（重写）父类的方法以提供自己的实现。

下面是一个简单的例子来说明继承的概念：

```java
// 父类
public class Animal {
    private String name;

    public Animal(String name) {
        this.name = name;
    }

    public void eat() {
        System.out.println(name + " is eating.");
    }
}

// 子类
public class Cat extends Animal {
    public Cat(String name) {
        super(name);
    }

    public void meow() {
        System.out.println("Meow!");
    }
}

// 测试类
public class Test {
    public static void main(String[] args) {
        Cat cat = new Cat("Tom");
        cat.eat();  // 继承自父类 Animal 的方法
        cat.meow(); // 子类自己的方法
    }
}
```

在上面的例子中，有一个父类 `Animal`​ 和一个子类 `Cat`​。子类 `Cat`​ 继承了父类 `Animal`​ 的属性和方法。通过使用关键字 `extends`​，子类 `Cat`​ 声明了它是从父类 `Animal`​ 继承而来的。

父类 `Animal`​ 有一个属性 `name`​ 和一个方法 `eat()`​，子类 `Cat`​ 继承了这两个成员，并且还新增了自己的方法 `meow()`​。在测试类的 `main`​ 方法中，我们创建了一个 `Cat`​ 对象 `cat`​，并调用了继承自父类的 `eat()`​ 方法和子类自己的 `meow()`​ 方法。

继承使得子类可以共享父类的属性和方法，同时可以在子类中添加特定的功能。这样可以提高代码的重用性和扩展性，同时形成更好的代码组织结构

在给定的例子中，`Cat`​ 类有一个构造函数：

```java
public Cat(String name) {
    super(name);
}
```

这是一个带有一个参数的构造函数，参数类型为 `String`​，参数名称为 `name`​。构造函数的作用是在创建 `Cat`​ 对象时初始化对象的状态。

构造函数的内部调用了 `super(name)`​，其中 `super`​ 关键字表示调用父类的构造函数。在这里，它调用了父类 `Animal`​ 的构造函数，并将 `name`​ 参数传递给父类的构造函数。

父类 `Animal`​ 的构造函数在这里是被子类 `Cat`​ 的构造函数调用的，通过 `super(name)`​，子类可以将传入的 `name`​ 参数传递给父类进行初始化。这样，父类 `Animal`​ 中的 `name`​ 属性就被正确地设置为传入的值。

因此，当创建 `Cat`​​ 对象时，需要提供一个 `String`​​ 类型的参数，用于初始化 `name`​​ 属性。例如：`Cat cat = new Cat("Tom");`​​

‍

# Overriding

方法重写（Method Overriding）是指子类重新定义（覆盖）父类中具有相同名称和参数列表的方法。子类通过重写父类的方法，可以提供自己的实现逻辑，从而改变了方法在子类中的行为。

重写方法的要求是方法名、参数列表和返回类型必须与父类中的方法相同或兼容。子类方法不能比父类方法拥有更严格的访问修饰符，但可以拥有更宽松的访问修饰符。

下面是一个例子来说明方法重写的概念：

```java
// 父类
public class Animal {
    public void makeSound() {
        System.out.println("The animal makes a sound.");
    }
}

// 子类
public class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("The cat says 'Meow!'");
    }
}

public class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("The dog says 'Woof!'");
    }
}
// 测试类
public class Test {
    public static void main(String[] args) {
        Animal animal1 = new Cat();
        Animal animal2 = new Dog();

        animal1.makeSound();  // 输出：The cat says 'Meow!'
        animal2.makeSound();  // 输出：The dog says 'Woof!'
    }
}
}
```

在上面的例子中，有一个父类 `Animal`​ 和一个子类 `Cat`​。父类中有一个 `makeSound()`​ 方法，它输出 "The animal makes a sound."。子类 `Cat`​ 通过使用 `@Override`​ 注解来重写了父类中的 `makeSound()`​ 方法，并提供了自己的实现逻辑，输出 "The cat says 'Meow!'"。

在测试类的 `main`​ 方法中，我们创建了一个 `Animal`​ 对象 `animal`​ 和一个 `Cat`​ 对象 `cat`​。当调用 `animal.makeSound()`​ 时，执行的是父类 `Animal`​ 中的 `makeSound()`​ 方法，输出了父类的信息。而当调用 `cat.makeSound()`​ 时，执行的是子类 `Cat`​ 中重写的 `makeSound()`​ 方法，输出了子类自己的信息。

通过方法重写，子类可以改变继承自父类的方法的行为，使其适应子类的特定需求。这样可以实现多态性，使得代码更灵活和可扩展。

‍

在测试类的 `main`​ 方法中，我们创建了一个 `Animal`​ 对象 `animal1`​，它引用了一个 `Cat`​ 对象；还创建了一个 `Animal`​ 对象 `animal2`​，它引用了一个 `Dog`​ 对象。然后，通过这些对象的引用调用 `makeSound()`​ 方法。由于多态性的存在，程序会根据实际对象的类型来动态绑定相应的方法，从而输出正确的声音信息。

这就是多态性的体现，通过父类类型的引用来引用子类对象，并根据实际对象的类型调用相应的方法，实现了多态性的效果。

# 抽象类和抽象方法

抽象类是在面向对象编程中用来表示概念上的、不可实例化的类。它是一种特殊的类，不能直接创建对象，而只能用作其他类的父类（基类）。

抽象类通过在类声明中使用 `abstract`​ 关键字进行标识。它可以包含抽象方法和非抽象方法。

抽象方法是没有实现的方法，只有方法签名（包括方法名、参数列表和返回类型）。子类必须实现（重写）抽象类中的抽象方法才能被实例化。

抽象类可以包含非抽象方法，这些方法具有实现代码。子类可以直接继承并使用这些非抽象方法，而无需重写。

抽象类通常用于建模抽象的概念、定义共享的行为和属性，并作为具体子类的模板。它可以提供一组通用的方法和字段，以便子类可以继承和扩展。

```java
abstract class Shape {
    protected String color;

    public Shape(String color) {
        this.color = color;
    }

    public abstract double calculateArea();
    public abstract double calculatePerimeter();

    public void displayColor() {
        System.out.println("Color: " + color);
    }
}
```

在这个抽象类中，我们定义了抽象方法 `calculateArea()`​ 和 `calculatePerimeter()`​ 来计算形状的面积和周长。这些方法没有具体的实现，而是留给具体的子类来实现。我们还定义了非抽象方法 `displayColor()`​ 来显示形状的颜色，这个方法有具体的实现代码。

然后，我们可以创建具体的子类来表示不同的形状，例如矩形、圆形和三角形：

```java
class Rectangle extends Shape {
    private double length;
    private double width;

    public Rectangle(String color, double length, double width) {
        super(color);
        this.length = length;
        this.width = width;
    }

    public double calculateArea() {
        return length * width;
    }

    public double calculatePerimeter() {
        return 2 * (length + width);
    }
}

class Circle extends Shape {
    private double radius;

    public Circle(String color, double radius) {
        super(color);
        this.radius = radius;
    }

    public double calculateArea() {
        return Math.PI * radius * radius;
    }

    public double calculatePerimeter() {
        return 2 * Math.PI * radius;
    }
}

class Triangle extends Shape {
    private double side1;
    private double side2;
    private double side3;

    public Triangle(String color, double side1, double side2, double side3) {
        super(color);
        this.side1 = side1;
        this.side2 = side2;
        this.side3 = side3;
    }

    public double calculateArea() {
        // Implement the calculation for triangle area
    }

    public double calculatePerimeter() {
        return side1 + side2 + side3;
    }
}
```

每个具体的子类都继承自抽象类 `Shape`​，并实现了抽象方法 `calculateArea()`​ 和 `calculatePerimeter()`​，提供了特定形状的计算逻辑。

通过使用抽象类和抽象方法，我们可以在设计中抽象出共同的特征和行为，提高代码的可读性和可维护性。同时，我们也可以通过多态性来统一处理不同形状的对象，简化代码逻辑。例如：

```java
Shape rectangle = new Rectangle("Red", 5, 4);
Shape circle = new Circle("Blue", 3);

rectangle.displayColor(); // Output: Color: Red
double rectangleArea = rectangle.calculateArea();
double rectanglePerimeter = rectangle.calculatePerimeter();

circle.displayColor(); // Output: Color: Blue
double circleArea = circle.calculateArea();
double circlePerimeter = circle.calculatePerimeter();
```

在这个例子中，我们可以使用抽象类 `Shape`​ 来创建不同形状的对象，并调用统一的方法来获取面积、周长和显示颜色，无需关心具体的子类类型。这展示了抽象类和抽象方法在实现多态性和简化代码逻辑方面的作用。

抽象方法本身是没有具体实现代码的。它只是一个声明，定义了方法的名称、参数列表和返回类型，但没有方法体。

例如，在之前的示例中，抽象类 `Shape`​ 中的抽象方法 `calculateArea()`​ 和 `calculatePerimeter()`​ 就没有具体的代码实现。这些方法只有方法签名，用来指定方法的输入和输出。具体的子类（如 `Rectangle`​、`Circle`​、`Triangle`​）必须实现这些抽象方法，并提供特定形状的计算逻辑。

抽象类不能被直接实例化，只能作为其他类的父类被继承。抽象类的主要目的是作为其他相关类的通用模板或基类，提供共享的属性和方法。

# toString方法

`toString()`​ 方法是 Java 中的一个方法，它用于将对象转换为字符串表示形式。

在 Java 中，所有的类都继承自 `Object`​ 类，而 `Object`​ 类中包含了一个默认的 `toString()`​ 方法的实现。默认的 `toString()`​ 方法返回一个字符串，格式为 "类名@哈希码"，例如 "ClassName@123456"。这种默认的字符串表示形式对于调试和日志记录可能不够有用。

为了提供更有意义和可读性的对象字符串表示形式，我们可以在自定义类中重写 `toString()`​ 方法。通过重写 `toString()`​ 方法，我们可以根据对象的属性和状态，返回一个描述对象的字符串。

例如，假设我们有一个名为 `Person`​ 的类，包含姓名和年龄属性。我们可以在 `Person`​ 类中重写 `toString()`​ 方法，以便返回包含姓名和年龄信息的字符串表示形式，例如 "Name: John, Age: 25"。这样，在使用 `System.out.println()`​ 或其他需要字符串表示的地方，就可以直接输出 `Person`​ 对象的信息，而不是默认的哈希码字符串。

重写 `toString()`​ 方法可以提高代码的可读性和调试效果，方便我们查看对象的内容和状态

```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("John", 25);
        System.out.println(person); // 输出：Person@1f32e575
    }
}
```

在上述示例中，`Person`​ 类没有重写 `toString()`​ 方法，因此默认的 `toString()`​ 方法会返回类名和哈希码的字符串表示。

现在，让我们重写 `toString()`​ 方法来提供更有意义的字符串表示：

```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person [Name: " + name + ", Age: " + age + "]";
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("John", 25);
        System.out.println(person); // 输出：Person [Name: John, Age: 25]
    }
}
```

在这个示例中，我们重写了 `Person`​ 类的 `toString()`​ 方法，返回一个包含姓名和年龄信息的字符串表示。现在，当我们打印 `person`​ 对象时，会输出更有意义的字符串表示形式。
