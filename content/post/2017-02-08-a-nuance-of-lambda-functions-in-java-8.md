---
categories:
- professional
date: "2017-02-08T00:00:00Z"
tags:
- java
- programming
title: A Nuance of Lambda Functions in Java 8
---
As I was trying to solve part 2 of the [Day 6 problem](https://github.com/sujithpl/advent-of-code-2015-java) in the [Advent of Code 2015](https://adventofcode.com/2015) challenge using Java 8, I ran into a curious problem. I had defined functions as follows for the various operations.

```java
public static Function<Integer, Integer> turnUp = i -> i++;
```

However, the solution from my program did not match the official answer. At first glance, I could not figure out the cause for the discrepancy. But after thinking about it for a while, I had a “a-ha moment” and wondered if the [postfix version of the increment operation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/op1.html) was the source of my issue. So I modified the functions to a prefix version as follows.

```java
public static Function<Integer, Integer> turnUp = i -> ++i;
```

Sure enough, the solution from my program matched the answer after this change.

The lesson here is that if you are relying on an implicit return from your lambda function, then you should use the prefix version of unary operations. That will ensure that the operation is performed before rather than after the return action.
