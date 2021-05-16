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





# Lecture 4

## Conditional Expressions

```haskell
abs :: Int -> Int
abs n = if n >= 0 then n else -n
```

一定要有一个else branch

### Guarded Equations

```haskell
abs n | n >= 0    = n
      | otherwise = -n
```



## Pattern Matching 

```haskell
not :: Bool -> Bool
not False = True
not True = False
```

_ 的意思是 matches any argument value 

### List Patterns 

[1,2,3,4]  = 1:(2:(3:4:[]))

```haskell
head :: [a] -> a 
head (x:_) = x 
tail :: [a] -> [a] 
tail (_:xs) = xs 
```



head tail作用于非空集合

## Lambda Expressions

λx → x + x  用λ可以不用写函数名

Why Are Lambda's Useful? （？）



## Operator Sections

reciprocation function(?)

1+2   = (+) 1 2



haskell 的 overloading？多态？



(Eq a, Num a) => (a,a) -> Bool  前面的限制？



# Lecture 5

## Set Comprehensions

## Lists Comprehensions 

```haskell
[x^2 | x <- [1..5]]
```

```haskell
[(x,y) | y <- [4,5], x <- [1,2,3]]
[(1,4), (2,4), (3,4), (1,5), (2,5), (3,5s)]
```

## Dependant Generators

```haskell
concat :: [[a]] -> [a]
concat xss = [x | xs <- xss, x <- xs]
```

(?)