# Week2

# Floating-point Types

```java
  double f = 4.35;
  System.out.println(100 * f); 
```

会发生错误，会输出`434.99999999999994`​

```java
double balance = 13.75;
  int dollars = balance; // Error
```

将浮点值传递给整形变量是错误的

## Round error

```java
public class Main {
public static void main(String[] args) {
double double1 = 1.00;
double double2 = 1.11;
System.out.println("10 * 1.00 :" + 10 * double1);
System.out.println("10 * 1.11 :" + 10 * double2);
}
}
```

最好使用BigDecimal类来计算小数或int转换为double(避免使用double)

```java
public class Main {
public static void main(String[] args) {
BigDecimal a = new BigDecimal("0.01"); // define by String 
BigDecimal b = new BigDecimal(0.01); //define by double
BigDecimal c = new BigDecimal("0.01"); // define by String 
System.out.println("string a + c:" + a.add(c));
System.out.println("double b + c:" + b.add(c)); 
}
}
```

new string和string

Create a String object:

* String str1 = “HelloWorld";

* String str2 = new String(" HelloWorld ");

* > 这两个字符串的区别在于它们的初始化方式和内容。
  >
  > 第一个字符串 str1 是通过字面值方式初始化的，即直接将字符串 HelloWrold 直接赋值给变量 str1。这是 Java 中常见的一种字符串初始化方式。
  >
  > 第二个字符串 str2 是通过 new 操作符创建的一个新的 String 对象，其值为 " HelloWorld "（注意字符串前后的空格）。这种初始化方式会在堆上创建一个新的 String 对象，无论是否已经存在相同值的字符串对象。
  >
  > 因此，str1 和 str2 除了内容不同之外，还有以下区别：
  >
  > 1. str1 存储在字符串常量池中，而 str2 存储在堆中。
  > 2. str1 是不可变的，因为它是通过字面值初始化的。而 str2 可以修改，因为它是通过 new 操作符创建的。
  > 3. str1 的创建方式更加高效，因为它不需要在堆上分配内存。而 str2 的创建方式需要在堆上分配内存，因此更加耗费资源。
  >
  > 总的来说，如果不需要在运行时动态创建字符串，应该尽可能使用字面值方式来初始化字符串。这样可以提高性能和效率。
  >

```java
public class Main {
    public static void main(String[] args) {
        String str1 = new String("abc");
        String str2 = new String("abc");
        System.out.println(str1 == str2); // false
        System.out.println(str1.equals(str2)); //true
   }
}
```

> 这是因为在 Java 中，== 运算符用于比较两个对象的引用是否相同，即判断两个对象是否是同一个对象。而 equals() 方法用于比较两个对象的内容是否相同。
>
> 在这个例子中，str1 和 str2 是通过 new 操作符创建的两个不同的对象，它们的引用地址不同，因此使用 == 运算符比较时返回 false。这表明 str1 和 str2 不是同一个对象，它们是在内存中不同的对象。
>
> 然而，由于它们的内容都是 "abc"，因此使用 equals() 方法比较时会返回 true，这表明它们的内容相同。这是因为 equals() 方法是在 String 类中被重写的，它会比较两个字符串的内容是否相同，而不是比较它们的引用地址。
>
> 总之，当需要比较两个字符串的内容时，应该使用 equals() 方法而不是 == 运算符。只有在需要比较两个对象的引用地址时才使用 == 运算符。

# Conditional Statement

* Executes code on the basis of some test

  * If condition
  * Then action
  * Else action
* Conditions are expressions that can be either TRUE or FALSE(条件为True或False的表达式)
* Boolean expressions（布尔表达式）

  * And: `&&`​
  * Or:`||`​
  * Not:`!`​

# 条件语句

* 格式1：

```java
if (关系表达式){
	语句体；
}
```

* 格式2：

```java
if (关系表达式){
	语句体1；
}else{
	语句体2；
}
```

* 格式3：

```java
if (关系表达式1){
	语句体1;
}else if(关系表达式2){
	语句体2;
}
else{
	语句体n+1;
}
```

# Comparing Strings

* Don't use == for strings!

  不要使用"=="
* Use equals method:  

  ​`if (input.equals("Y"))`​
* Case insensitive test ("Y" or "y")  

  ​`if (input.equalsIgnoreCase("Y")) ​`​

  ​`String s,t; ​`​

  ​`s.compareTo(t) < 0`​

# Switch语句

```java
public class SwitchDemo{
public static void main(String[] args){
Scanner keyboard = new Scanner(System.in); 
int number; // To hold keyboard input 
System.out.print("Enter a number between 1 and 5”);
number = keyboard.nextInt();
switch (number){
case 1:
System.out.println("You entered 1.");
break;
case 2:
System.out.println("You entered 2.");
break;
case 3:
System.out.println("You entered 3");
break;
case 4:
System.out.println("You entered 4");
break;
case 5:
System.out.println("You entered 5");
break;
default:
System.out.println(“Incorrect answer");
}
}
}
```

# do-while Loop

* The do-while loop is a post-test loop, which means it will execute the loop prior to testing the condition.

* The do-while loop (sometimes called called a do loop) takes the form:

  ```java
  do
  {
  statement(s);
  }while (condition);
  ```

# 数组

**数组的定义格式**：  
（1）格式1：数据类型[ ] 变量名，例如：int [ ] arr。定义了一个int类型的数组，数组名是arr。  
（2）格式2：`数据类型 变量名[ ]={..,..,..,..}`​， 例如：int arr[ ]。定义了一个int类型的变量，变量名是arr数组

**初始化：**为数组中的数组元素分配内存空间，并为每个数组元素赋值

**数组初始化类型：**动态初始化、静态初始化

* **动态初始化：**初始化时只指定数组长度，由系统为数组分配初始值

  * 格式：数据类型[] 变量名=new 数据类型[数组长度]，例如:`int[] arr=new int[3]`​

‍

# **i++和++j**

i++ 是一个后缀递增操作符，它的作用是先返回变量 i 的当前值，然后再将 i 的值加 1。在 i++ 表达式执行后，i 的值会增加 1。因此，i++ 表达式会产生一个副作用，即会修改变量 i 的值。

例如，考虑下面的代码：

```java
int i = 0;
int j = i++;
```

在这个例子中，i++ 表达式将 i 的值加 1，并将其返回给变量 j。因此，j 的值为 0，而 i 的值为 1。

相比之下，++j 是一个前缀递增操作符，它的作用是先将变量 j 的值加 1，然后再返回 j 的新值。因此，在 ++j 表达式执行后，j 的值会增加 1，但这个操作不会影响其他变量的值。

例如，考虑下面的代码：

```java
int i = 0;
int j = ++i;
```

在这个例子中，++i 表达式将 i 的值加 1，并将其返回给变量 j。因此，j 的值为 1，而 i 的值也为 1。

因此，i++ 和 ++j 之间存在差异，它们的执行顺序和返回值是不同的。在使用时应根据实际需要进行选择。

# Introduction to Arrays

•The variables that we have used so far only allow us to store a single value.

•Arrays allow us to store a sequence of values of the same type.

•An array can store any type of data but only one type of data at a time.

•An equivalent data type to a list called ArrayList will be seen in week 6
