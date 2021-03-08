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