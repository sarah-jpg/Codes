[TOC]





# Lecture 1





# Lecture2

## SOLVING PROBLEM BY SEARCHING

Exhaustive search穷举搜索法

eg1. 

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\8f076e8f574526d6cb8b456a4501ee3.png" alt="8f076e8f574526d6cb8b456a4501ee3" style="zoom:33%;" />

## PROBLEM FORMULATION

 process of deciding what actions and states to consider, given a goal

## PROBLEM COMPONENTS

- ### Initial State

- ### Actions(Operators)

- ### Goal Test 

- ### Path  Cost

state space -  The initial state and the successor function define the state space which is the set of all states reachable from the initial state



eg. ROMANIA

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\0fd35ef1a1325ef61ff46b863a559c2.png" alt="0fd35ef1a1325ef61ff46b863a559c2" style="zoom:33%;" />

eg. 8-PUZZLE

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\7f3b18b530090a50bb633a531172662.png" alt="7f3b18b530090a50bb633a531172662" style="zoom:33%;" />

eg. 8-QUEEN

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\e45c2de043c28d99e624c864f79b469.png" alt="e45c2de043c28d99e624c864f79b469" style="zoom:33%;" />

(?)

## TREES - TERMINOLOGY

Nodes

- Root node
- Children/parent of nodes
- Leaves

Branches

Average branching factor

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\e8bcfeccdd1e2077ee1c824e5b2ad01.png" alt="e8bcfeccdd1e2077ee1c824e5b2ad01" style="zoom:33%;" />

Depth

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\b357d0dc28750fd7917042c9a654eed.png" alt="b357d0dc28750fd7917042c9a654eed" style="zoom:33%;" />

Tree size 

<img src="C:\Users\HP\AppData\Local\Temp\WeChat Files\1a01ff2d16fc64707e91758650c73c6.png" alt="1a01ff2d16fc64707e91758650c73c6" style="zoom:50%;" />

## PROBLEM REPRESENTATION

- States - nodes
- Initial State - root node
- State Space - all nodes in the tree
- Neighborhood
- Operators-branches

## FINDING GOALS IN TREES: REALITY

## SEARCH TREE ISSUES

### branching factor

The size of the search tree



# Lecture 3

complete search



good solution

- path cost(?)
- search post(time and memory)

## Evaluation criteria

- completeness 如果找到了返回，没有找到所有遍历一遍
- time complexity

total number of nodes in the tree

- space complexity

number of leaves

- optimality

## Time and space complexity

- branch
- depth
- maximum depth

## BLIND SEARCHES

"Expand"

"Test"

（写一下queue里面的改变方法）

## Comparation



|      | BREADTH FIRST SEARCH (BFS)| DEPTH FIRST SEARCH|UNIFORM COST SEARCH|
| ---- | ---- | ---- |----|
|completeness|yes  |no      |   |
|time complexity| O(b^d) | O(b^m) |   |
|space complexity| O(b^d) | O(bm) |   |
|optimality| yes | no | yes |



### GENERAL TREE SEARCH




sort



# Lecture 6

1. component
2. prior knowlege
3. representation of knowledge
4. feedback/output/label

Date -> ML -> Model



## process of ML

data set 分为 Training set and Test set

- random
- k-fold cross validation

dataset中有 categorical = discrete / continuous = numerical



### SUPERVISED LEARNING

#### classigication(discrete)

#### regression(continuous)



### UNSUPERVISED LEARNING

没有label

#### Clustering（discrete)

#### Dimensional Reduction(continuous)



## Data mining 

### Task

Predictive

Desciptive



#### Classification 

regression

decision tree

neural networks

#### CLUSTERING

Partitioning-based clustering

Density-based clustering



# Lecture 7

## Neural networks

weight on a path positive - excitatory

negative - inhibitory