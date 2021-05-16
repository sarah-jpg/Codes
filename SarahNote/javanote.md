[TOC]



# Lecture 3

抽象的目的是产生类，而类的目的是创建具有属性和功能的对象

## Classes

templates or blueprints/specify how to build objects 某一类型

## Objects

instances of class 对象



## 4 key principles of OOP

Encapsulation/Abstraction(protect)/Inheritance/Polymorphism（overload, override)



```java
class classname{
    //declare instance variables
    type varname;
    
    //declare constructors 
    classname(parameters){
        //body of constructors
    }
    
    type methodname(parameters){
        //body pf method
    }
    
}
```

Constructors are the same name as class but with parameters

跟c的sturcture类似



## Reference variables

class在heap memory中

```java
class Vehicle{
    int passengers, fuelCap, mpg;
}

class VihicleDemo{
    public static void main(String[] args){
        Vehicle van = new Vehicle();
        Vehicle car = new Vehicle();
        car.mpg = 25;
        car,fuelCap = 12;
    }
}
```

car.mpg       car-reference variable     mpg-instance variable



## Assignment of reference variables

## Methods

```java
return-type methodname(parameters){
	statements;
}
```

## Returning a Value

## Constructors 

初始化class

## This



refer to the object on which the method is called

useful when referring to an instance variable

因为instance variable和parameter或者local会重名 前者就会加this

```java
// Java code for using this() to  
// invoke current class constructor 
class Test 
{ 
    int a; 
    int b; 
  
    //Default constructor 
    Test() 
    {   
        this(10, 20); 
        System.out.println("Inside  default constructor \n"); 
    } 
      
    //Parameterized constructor 
    Test(int a, int b) 
    { 
        this.a = a; 
        this.b = b; 
        System.out.println("Inside parameterized constructor"); 
    } 
  
    public static void main(String[] args) 
    { 
        Test object = new Test(); 
    } 
} 
```





# Lecture 4

## Fundamentals and terminology

All objects have a state(Fields-usually hidden) and behavior(Methods)



## Language basics

### Variables

- #### Instance variables(non-static)

在class里面在method外面

在初始化类时初始化

Values unique to each instance of a class but differ between instantiations 

- #### Class variables（static）

在class里面在method外面

在初始化类时初始化（不能在class里面被reinitialized）

Static keyword – Only one copy of this（？）and it is shared by all the objects of that class

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\465ac782503a5647250363685422398.png" alt="465ac782503a5647250363685422398" style="zoom:33%;" />

补充： Static keyword

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\8284760cb1bc320d4147c2fe933190a.png" alt="8284760cb1bc320d4147c2fe933190a" style="zoom:33%;" />



- #### Local Variables

Variables defined inside methods, constructors or blocks

## Keywords

Keywords are member dependent(?)

eg.

- static variables 
- static methods

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\bab487e4c36cbb87db1ce3a8b1d4090.png" alt="bab487e4c36cbb87db1ce3a8b1d4090" style="zoom:33%;" />

static method 里面不能call非static的东西/不能use

- static class

## Primitive Data Types

byte short int long

float double

boolean

char

## Object Data Types

Numbers

Strings - Objects that is an array of char

## Primitive Data Types vs Object Data Types

eg. int vs integar

int是基本数据类型，int变量存储的是数值。Integer是引用类型，实际是一个对象，Integer存储的是引用对象的地址

## Arrays

objects-hold fixed number of values

1. declare
2. allocate memory(size!!)       firstArrayInts = new int[3]
3. populate 第几个是几

### Multidimensional Arrays

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\53fab6be589e91aa52949a8bb186a58.png" alt="53fab6be589e91aa52949a8bb186a58" style="zoom:33%;" />

## Enhanced for loop

```java
class forEachTest {
    public static void main(String[] args) {
        char[] vowels = {'a', 'e', 'i', 'o', 'u'};
        for (char item: vowels) { //go through an array sequentially
            System.out.println(item);
		}
	}
}
```

## Break



### Unlabeled

```java
class BreakDemo {
    public static void main(String[] args) {
        int[] arrayOfInts = { 1, 2, 3, 4};
        int target = 2;
		int i;
		boolean found = false;
		for (i = 0; i < arrayOfInts.length; i++) {
		if (arrayOfInts[i] == target) {
			found = true;
			break;
		}
		System.out.println("how many times do we print this");
		}
		if (found) {
            System.out.println("Found " + target + " at index " + i);} else {
            System.out.println(target + " not in the array");
		}
		}
}

```



### labeled

如果不加loop1 只是跳出当前循环继续外圈循环 加了loop1之后就可以跳出大循环

```java
class LabelledLoop{
    public static void main(String args[]){
        int i,j;
        loop1: for(i=1;i<=10;i++)
        {
            for(j=1;j<=10;j++) //second loop
            {
                System.out.print(j + " ");
                if(j==5)
                    break loop1; //Statement 1
			}
		}
	}
} 
```

## Continue

skips the current iteration of a loop

## Length of an array

It has a length instance variable, decided on creation

## Strings

Need to create a new one every time

Can use subString Method

## Access Modifiers

- Top level 
  - public - – visible by all classes everywhere
- Member level
  - private - Can only be accessed by its own class
  - protected - own package (as with package-private) and by a subclass of its class in another package (eg extends….more later)

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\20bdc7c2effcad46c9df30a1befdea5.png" alt="20bdc7c2effcad46c9df30a1befdea5" style="zoom:50%;" />

（？）

## Passing Arguments to Methods

Primitives and references both passed by value using call-by-value 

- If the copied argument is primitive then changes made do not effect the original argument
- If the copied argument is a reference type then changes made do effect the object, because the reference to the object is copied

In Java objects are always 'passed by reference', they can never be 'passed by value'.

In Java we always use references to address objects（？)

## Method overloading

use the same name



Constructor overloading 



## Recursion



## Static variables

## Inner classes



## Question

1. p8 Static keyword – Only one copy of this

instance在memory space里面的位置是调用一次多增加一个位置， 而static始终一个位置，比如一个车子有四个轮子就应该用static，因为是固定的，不仅可以减少内存还可以保护代码

1. p12 Keywords are member dependent 

记住例子

1. p33 protected？p35 的package subclass world

同一类对其他类的保护

1. p36 

variable传递是复制值/object传递还有继续指向这个物体的

this有点像java的指针

1. pass value/referencnes 用this？

理解这个eg<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\3a693f8b82436eafad01806200a0f40.png" alt="3a693f8b82436eafad01806200a0f40" style="zoom:50%;" />







# Lecture 5



## Pass by reference and pass by value

当把一个值pass 是复制的值

当把一个object pass 是pass的通道

## Constructors vs methods

|   | Constructors     | methods     |
| ---- | ---- | ---- |
|      |initialize objects when they are created      |perform operations on objects that already exist      |
|      | called implicitly when the new keyword creates an object     |      |
|      | are called implicitly when the new keyword creates an object      | can be called directly on an existing object     |
| |must be named with the same name as the class name| must be called something different to the class name|
||can't return anything |must be configured return something, although it can be void|

## Static keyword 

Static methods can’t use the this keyword as there is no instance for  this to refer to(?)



## Inheritance

superclass - > subclass

Subclass inherits all the variables and methods of the superclass

Subclasses code can change the ‘intention’ of the superclass code



class Superclass {…..} 

class Subclass extends Superclass { .....}



### Every class is a subclass of Java’s Object class 

Each superclass can have many subclasses but in Java (as opposed to  C++) each class can have at most one superclass.



A subclass cannot access the private members of its superclass.

## Overriding

A method declared final or static cannot be overridden. 

Constructors cannot be overridden







# Lecture 6

Good programmers will always use the @Override annotation when  overriding

## Inner class

Methods in the outer class can instantiate the inner class(?)

```java
class Outer { 
    class Inner { 
    } 
}
```

### Static Inner Class

只可以调用外部static相关联的信息

外部类使用时，直接类名.信息

### Non-static inner Class

- #### Inner class（成员内部类）

可以调用外部所有信息

使用时要先new外部类

- #### Method local inner class（方法内部类）

仅存在于方法之中

- #### Anonymous inner class

定义的同时初始化

```java
Dog dog = new Dog(){
    public void someDog(){
        ...
    }
    
};
dog.someDog();
```



## Abstract

Any subclass of this class must contain implementations for all of the  abstract methods in its superclass class..(?)



is_a    用于继承  

has_a   是组合  一个类中包含了其他类

# Lecture 7

## Abstraction -> Interfaces

interface是一个纯抽象类（只有static和final变量）

### default

interface里面不能define方法但可以declare 如果要define 只能用default关键字



class extends class

class implements interface

interface extends interface



interface可以实现多重继承-一个子类有多个父类



## SOLID

准则

# Lecture 8

## Getters and Setters

设置get和set函数return和赋值 便于外部修改

## Abstract Classes and Interfaces

Abstract classes 0-100% abstraction

Interfaces 100% abstraction

## Super

super.color    instance variable

super. printMethod()  methods

super()  constructors  上一级要有constructor要不会报错



## Packages

package pkgname;

```java
import pkg.MyClass
```

packages and member access



### static import

比如 "Math.sqrt( ) 用了static之后就只用写 sqrt( )

## Types of polymorphism

Method overloading

Generics in Java

Subclass Polymorphism



### Generics

范型 eg. @Override

## Java ArrayList

这是一个类

java.util.AbstractList<E>   < >   里面的东西限制list类型

E – Element (used extensively by Collections, for example ArrayList) 

K, V – Key, Value (Used in Map) 

N – Number 

T – Type

## Time causes problems

java.time package

# Quiz

1. java的一个子类只能有一个父类（但能实现多个接口）， 一个父类可以有多个子类
2. class的根父类是 Object
3. java关键字 他们用来表示一种数据类型，或者表示程序的结构
4. java原始数据类型有short、byte、int、long、boolean、char、float、double
5. 有一种class不能被作为private ： outer（复习）
6. enhanced loops： easier array access



# Exception Handling

try-catch 的好处 （自己处理异常）

continue/meaningful error reporting



## Exception vs error 

error基本上是不可修复的



## Checked vs Unchecked exceptions

Checked 使用try-catch eg. FileNotfound Exception

Unchecked 自己能发现的 - logic error 运行过程中的问题（包括error）



## Throw（交给调用者处理）

用throw定义exception(checked/unchecked都可以用)

```java
public void setRadius (double newRadius) {
    if(new<5)
        throws IllegalArgumentException("No!");
}
```

### Throwing Exception

```java
public void setRadius (double newRadius) {
    throws IllegalArgumentException{
        if(...)
            ..
        else
            throw new IllegalArgumentException("..");
    }
}
```

这样写

```java
void p1(){
    try{
        p2();
    }
    catch(IOException ex){
        ...
    }
}

void p1() throws IOException{
    p2();
}
```

### Rethrowing 

```java
try{
    statements;
}
catch(TheException ex){
    perform operations before exits;
    throw ex;
}
```



### finally 

```java
try{
    statements;
}
catch(TheException ex){
    handling ex;
}
finally{
    finalStatements;
}
```

### throw vs throws

throw 是语句抛出一个异常

throw (异常对象);

throws是方法可能抛出异常的声明

public void doA(int a) throws Exception1,Exception3{......}





## Reading files

BufferedReader

```java
FileReader file = new FileReader(Stirng file);
BufferedReader buffer = new BufferedReader(file);
```



FileInputStream

File

Scanner

RandomAccessFile

FileReader

```java
import java.io.FileReader;
String fileName = "FRtest.txt";
FileReader input = new FileReader(fileName);
```

