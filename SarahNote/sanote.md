[TOC]

# Lecture 1 - Intro

## Classes of Computers(p19)

Personal Computers

Embedded Computers(嵌入式计算机)

Server Computers-large workloads

Supercomputers 

## The PostPc Era(p20)

Personal Mobile Device(PMD)

Cloud Computing

## 8 Great Ideas in Computer Architecture(p23)

Moore's Law

由于摩尔定律，设计时要设计结束时的工业水平，而不是开始的。

Use Abstraction to Simplify Design

Make the Common Case Fast

Performance via Parallelism

 Performance via Pipelining  流水线作业

Performance via Prediction

Hierarchy of Memories

Dependability via Redundancy





# Lecture 2

## Computer Components

Input

Output

Memory

Processor (CPU)

## The von Neumann Machine

## Below Your Program

Application software 

System software

​	Compiler

​	Operating system

Hardware

## Computer Systems Hierarchy

![9b739eb67c98c9f4089f98c93757602](C:\Users\HP\AppData\Local\Temp\WeChat Files\9b739eb67c98c9f4089f98c93757602.png)

## Instruction Set Architecture 



## Technology Trends



# Lecture 3

## Performance

### Response time

minimize execution time

$$
Performance_x =  1/Execution time_x
$$

Computer X is n times faster than Computer Y:

$$
Performanc e_x / Performanc e_Y = Execution time_Y/ Execution time_x = n
$$

#### Response time vs CPU time（包括User CPU time and System CPU time）

cpu time 不包括 I/O 和运行其他程序的时间

#### CPU clocking

clock cycle  - the time for one clock period, usually of the processor clock, which runs at a constant rate

CPU Time = CPU Clock Cycles * Clock Cycle Time 
         = CPU Clock Cycles / Clock Rate

clock frequency  - cycles per second, which is the inverse of the clock period

### Throughput(bandwidth) 

 The number of tasks completed per unit time

## Instruction Performance

depend on the number of instructions in a program

### Clock cycles per instruction (CPI)

the average number of clock cycles each instruction takes to execute

CPU Clock Cycles = Instruction Count * Cycles per Instruction (CPI)

### The Classic CPU Performance Equation



<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\0bda9e4b6e5da288c757622c0e52cda.png" alt="0bda9e4b6e5da288c757622c0e52cda" style="zoom:50%;" />

### CPI in More Details

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\b395140bd1e7aedd7210e325efc48bd.png" alt="b395140bd1e7aedd7210e325efc48bd" style="zoom:50%;" />



Instruction n Count - 总的count数

先算出Clock Cycles再除以n



CPU Time =  Instruction Count * CPI * Clock Cycle Time



## 



## Understanding Program Performance

- Algorithm
- Programming language
- Compiler 
-  ISA



## The Power Wall

晶体管的状态从0到1或者1到0需要消耗能量

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\25ccdf2f828cc24e8fe623b93ccaa4e.png" alt="25ccdf2f828cc24e8fe623b93ccaa4e" style="zoom:50%;" />

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\6f308b70b76baec7aff34c8676c4850.png" alt="6f308b70b76baec7aff34c8676c4850" style="zoom:50%;" />



## Real Stuff: SPEC CPU Benchmark

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\c3c344e22b401823c944e3466211a0c.png" alt="c3c344e22b401823c944e3466211a0c" style="zoom:50%;" />



## Amdahl’s Law

The performance enhancement possible with a given improvement is limited by the amount that the improved feature is used

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\a9389cb37efd0386027c7ad11ec39f9.png" alt="a9389cb37efd0386027c7ad11ec39f9" style="zoom:50%;" />

## Review

## 概念

### Relative performance = 1/Execution time  

Execution time = response time 计算机完成一个task的总时间(由其中instruction数量决定)

Throughput = bandwidth 一定时间内完成的task数量

Execution time 和 Throughput 被processor 影响（快一点的processor/多一些processor）

### Measuring performance 

Response time (同上， 包括disk access/memory access/ I/O activities)

CPU execution time (CPU time) 完成一个task的CPU花的时间(不包括I/O)(可以分成user CPU time， system CPU time)



Clock cycle(Clock tick) 一个clock period的时间 (通常是processor clock，是一个常量) ps ns

Clock frequency(Clock rate) 一定时间段的圈数 = 1/clock period GHz MHz

### Instruction Performance

CPI(Clock cycles per instruction) 由CPU hardware决定

Instruction count 由program ISA和compiler决定



### Program Performance

## 公式

CPU Time = CPU Clock Cycles * Clock Cycle Time 
                   = CPU Clock Cycles / Clock Rate

CPU Clock Cycles = Instruction Count * Cycles per Instruction (CPI)

CPU Time =  Instruction Count * CPI * Clock Cycle Time = Instruction Count * CPI/Clock Rate



# Lecture 4

## MIPS structure

Bit

Byte - a sequence of bits/= 8 bits

Word



### MIPS Introduction

Microprocessor without Interlocked Processor States

### Fetch-Execute Cycle

Fetch the instruction

Dode the instruction

Execute the instruction

Write back

### MIPS Basic Syntax

- .data - Start assembling data
- .text - Start assembling program instructions
- .asciiz - Place a null-terminated ASCII string in memory

### MIPS Registers

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\94847c4ae82ee6f5ae3a8b5f569b807.png" alt="94847c4ae82ee6f5ae3a8b5f569b807" style="zoom:50%;" />

### MIPS Instruction Field

- op - operation code
- rs - first source register operand
- rd - destination register operand
- shamt - shift amount
- funct - function code



### MIPS Instruction Format



## MIPS Arithmetic

### ADD

### SUBTRACT

### ADD IMMEDIATE

## Caller-saved Registers vs. Callee-saved Registers



Caller-saved Registers： $t0 - $t9  不保留 储存临时值

Callee-saved Registers： $s0 - $s7 保留 储存long-lived values

## System Call



## MIPS Branching

• beq a, b, l  goto instruction at label l if a==b,

• bne a, b, l goto instruction at label l if a!=b, otherwise, continue with the next  instruction

• j l – Jump to



### while 

```MIPS

loop: beq $s0,$zero,wexit #goto exit if i==0
	  addi $s0,$s0,-1 # i=i-1
      addi $s1,$s1,3 # j=j+3
      j loop # goto loop
wexit: … … # execution continues here
```

slt a,b,c      a有啥用



