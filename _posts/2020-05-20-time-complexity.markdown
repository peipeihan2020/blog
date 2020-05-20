---
layout: post
title: "Time Complexity"
date: 2020-05-20
description: Time complexity of an algorithm quantifies the amount of time taken by the algorithm to run as a function of the length of the input.
img:  bigo/topic.png
use_math: true
---

> Time complexity of an algorithm quantifies the amount of time taken by the algorithm to run as a function of the length of the input.

The execution time of an algorithm depends on a lot of facts such as hardware, operating systems, processors, etc. It's very hard to measure real execution time. Even we can get the time, it's not stable and therefore useless. 
Bellow are the two succession submissions of the same algorithm in leetcode within 1 minute. As we can see, the runtime is different. 
![image](../assets/img/bigo/formula.png)
![image](../assets/img/bigo/formula2.png)


So instead we calculate the number of elementary operations, assuming the elementary operations take a fixed amount of time to perform.
An elementary operation is one whose execution time is bounded by a constant for a particular machine and programming language. That means if we run an elementary operation written in a specific language on a specific machine, it always takes the same time to be executed. Such as assignment, addition, multiplication, etc.

There is still another problem with this which is the number of elementary operations of an algorithm may vary among different inputs of the same size.  for example

![image](../assets/img/bigo/formula3.png)

The number of elementary operations of this algorithm with input `x=1` and `x=3` is different.
In this case, there are two ways to compute the time complexity.
The most common case is worst-case time complexity, which is the maximum amount of elementary operations required for inputs of a given size.
The less common case is average-case time complexity, which is the average of the number of elementary operations required for a finite number of possible inputs of a given size.

In both cases, the time complexity is expressed as a function of the input size, which is difficult to compute. And the time complexity for small input size is usually not consequential.
So one common approach is focusing on the asymptotic behavior of the complexity.

> Asymptotics is a method of describing limiting behavior.
As an illustration, suppose we  are interested in the properties of a function f(n) as n becomes very large. If $f(n) = n^2 + 3n$ , when n becomes very large, 3n becomes insignificant compare to $n^2$. The function f(n) is said to be "asymptotically equivalent to $n^2$， as n$\to \infty$" 

Therefore, the time complexity is commonly expressed using big O notation regarding the input size, such as O(1), O(n), O($n^2$), O($log^n$). Here, 1, n, $n^2$ and $log^n$ are the asymptotics of the time complexity functions.
Then how to get big O.
First we need to calculate the number of elementary operations in the worst case. Then we pick the most significant part of the result and remove the constant before it.
For example, if the number of elementary operations of an algorithm is $2n^2+3n+4$. Based on the asymptotics, $2n^2$ is the most significant part. As $n \to \infty$,  the influence of the leading constant 2 actually becomes trivial. So the time complexity in big O notation is $O(n^2)$.
Now, let's have some examples to see how we compute time complexity.
1. O(1)
```python
def first(x):
	 f = first(x)   
	 return f
```
This algorithm has two elementary operations. Suppose the execution time of them is both 1. So the total execution time is 2 and therefore the big O notation of this algorithm is O(1) which means it takes constant time to run. It does not depend on the size of the input.
2. O(n) where n is the input size.
```python
def loop(x):
     n = len(x)
	 sum = 0
	 for i in range(n):
		 sum += i   
	 return sum
```
First step, identify the number of the elementary operations. There 2 ones before the for loop and 1 return operation. The different part is the one inside the for loop. This operation is executed n times. So the total number of elementary operations is n + 3. Then the time complexity is O(n).