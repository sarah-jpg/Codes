[TOC]



# Chapter 1

# Chapter 2

## Use as a calculator

## The standard prelude

## Function Application

Moreover, function application is assumed to have  higher priority than all other operators

f a + b -> (fa) + b



## Haskell Scripts

:reload 修改代码后重新载入

:quit      quit GHCi 

:type expr    show type of expr

x 'f' y is just syntactic sugar for f x y

不能用tab可能会报错（只能用space）

缩进的bug

## Naming Requirements

list arguments usually have an s suffix on their name

eg. xs ns nss



# Chapter 3

## Types

类型不同的运算会自动报错

e ：：t(？)



### Basic Types 

Bool / Char/ String/ Int(固定精度)/Integar(任意长度)/Float

### List Types

A list is sequence of values of the same type/variable length

[]

[False,True,False] :: [Bool]



### Tuple Types

A tuple is a sequence of values of different types/fixed length and position

()

(False,’ a ’,True) :: (Bool,Char,Bool)

(True,[’ a ’ , ’b’]) :: (Bool,[Char]) 

(1, 'c') ('c', 1) 在有的时候是不同的- 都在列表里面的时候 多个元素

### Function Types

t1 → t2 is the type of functions that map  values of type t1 to values to type t2

### Curried Functions

Functions with multiple arguments are also possible  by returning functions as results

```haskell
add’ :: Int → (Int → Int)  

add’ x y = x+y
```

把x交给add' 返回add' x   接下来y传过去返回一个x+y

（每个Int分别代表什么 - 没有特定的意思 只需要理解下面一行正着来 后面一行倒着来 写成 x的类型 -> y的类型 -> x+y的类型）

Functions that take their arguments one at a  time are called curried functions



#### Why is Currying Useful?(?)



Int → Int → Int → Int   =  Int → (Int → (Int → Int))

mult x y z = ((mult x) y) z

### Polymorphic Functions 

its type contains one or more type variables



length :: [a] → Int    For any type a, length takes a list of  values of type a and returns an integer

fst :: (a,b) -> a

head :: [a] -> a

take :: Int -> [a] -> [a]

zip :: [a] -> [b] -> [(a,b)]

id :: a->a

(?)