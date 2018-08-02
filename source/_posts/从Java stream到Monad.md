---
title: 从Java stream到Monad
date: 2018-07-31 08:38:45
tags:
- Java stream
- Monad
mp3: http://domain.com/awesome.mp3
cover: https://picsum.photos/1600/900/?random
---

### 从Java stream到Monad

​	在Java中，就算初学Java的小伙伴对stream的概念应该也不陌生，因为stream这个名词在Java I/O中被广泛应用。当时大家的理解应该是：stream是一组有顺序的，有起点和终点的字节集合，是对数据传输的总称或抽象 。 但是在今天我们讲的stream和I/O中的概念完全不同，这里我们先Stream入手，学习[Stream API](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html)的具体使用，然后再引入一个抽象的概念[Monad](https://en.wikipedia.org/wiki/Monad_%28functional_programming%29),从理论上理解Stream的原理和设计思想，让你对什么是函数是编程初窥门径。

​	首先小伙伴们要明白，我们操作stream的目的其实和操作collection一样，通过对一个集合中的元素进行计算，得到一个新的元素集合。



> In [functional programming](https://en.wikipedia.org/wiki/Functional_programming), a **monad** is a [design pattern](https://en.wikipedia.org/wiki/Design_pattern) that defines how functions, operations, inputs, and outputs can be used together to build [generic types](https://en.wikipedia.org/wiki/Parameterized_type),[[1\]](https://en.wikipedia.org/wiki/Monad_%28functional_programming%29#cite_note-1) with the following organization:
>
> 1. Define a data type, and how values of that data type are combined.
> 2. Create functions that use the data type, and compose them together into operations, following the rules defined in the first step.

​	上面的引用出自wikpedia,说了一大堆，相信大家都不想看，我也没看懂，但是上面明确说了**monad is a design pattern**. 那么问题来了，什么又是design pattern？我们继续点开连接查看：

> A **design pattern** is the re-usable form of a solution to a design problem.

The lowercase [Greek](https://en.wikipedia.org/wiki/Greek_alphabet) letter λ ([lambda](https://en.wikipedia.org/wiki/Lambda)) is an unofficial symbol of the field of programming language theory.  
