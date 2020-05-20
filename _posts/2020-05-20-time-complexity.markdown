---
layout: post
title: "Time Complexity"
date: 2020-05-07
description: Time complexity of an algorithm quantifies the amount of time taken by the algorithm to run as a function of the length of the input.
img:  # Add image post (optional)
use_math: true
---

> Time complexity of an algorithm quantifies the amount of time taken by the algorithm to run as a function of the length of the input.

Execution time of an algorithm depends on a lot of facts such as hardware, operating systems, processors, etc
It's very hard to measure real execution time. Even we can get the time, it's not stable. 
Bellow are the two succession submissions of the same algorithm in leetcode within 1 minute. As we can see, the runtime is different. 
![image](../assets/img/bigo/formula.png)
![image](../assets/img/bigo/formula2.png)


So instead we calculate the number of elementary operations, assuming the elementary operations take a fixed amount of time to perform.
An elementary operation is one whose execution time is bounded by a constant for a particular machine and programming language. That means if we run an elementary operation written in a specific language and a specific machine, it always takes the same time to be executed.

The number of elementary operations of an algorithm may vary among different inputs of the same size.  Take bellow algorithm`cal ` for example
![image](../assets/img/bigo/formula3.png)
The time complexities of this algorithm with input `x=1` and `x=3` are different.
In this case, there are two ways to compute the time complexity.
The most common case is worst-case time complexity, which is the maximum amount of elementary operations required for inputs of a given size.
The less common case is average-case time complexity, which is the average of the number of elementary operations required for a finite number of possible inputs of a given size.

In both case, the time complexity is expressed as a function of the input size, which is difficult to compute. And the time complexity for small input size is usually not consequential.
So one common approach is focusing on the asymptotic behavior of the complexity.

> Asymptotics is a method of describing limiting behavior.
As an illustration, suppose we  are interested in the properties of a function f(n) as n becomes very large. If $f(n) = n^2 + 3n$ , when n becomes very large, 3n becomes insignificant compare to n2. The function f(n) is said to be "asymptotically equivalent to $n^2$， as n$\to \infty$" 

Therefore, the time complexity is commonly expressed using big O notation regarding the input size, such as O(1), O(n), O($n^2$), O($log^n$). Here, 1, n, $n^2$ and $log^n$ are the asymptotics of the time complexity functions.