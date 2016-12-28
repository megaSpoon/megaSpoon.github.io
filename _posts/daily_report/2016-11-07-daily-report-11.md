---
layout: post
title: Daily Report - 11/07
description: "daily report -- record what I learned today"
modified: 2016-11-01
tags: [daily log, ]
image:
  feature: Bathers on the Beach.jpg
  credit: Erich Heckel
  creditlink: https://en.wikipedia.org/wiki/Erich_Heckel
---

11-07-2016-01

[***problem***]can't install octave packages on CentOS 7. It always give me an error like this:

```
pkg: unable to find the mkoctfile command, Octave installation is incomplete
error: called from '__gripe_missing_component__' in file /usr/share/octave/3.8.2/m/help/__gripe_missing_component__.m near line 53, column 3
error: called from:
error:   /usr/share/octave/3.8.2/m/pkg/private/install.m at line 201, column 5
error:   /usr/share/octave/3.8.2/m/pkg/pkg.m at line 394, column 9
```

Also, it will make Intel MKL BLAS lib not loaded. I don't know why. Maybe it uses its own built-in BLAS lib like OpenBLAS.

[***Solution***] NA

Scala predef objects

The Predef object provides definitions that are accessible in all Scala complitaion units without explicit qualification.

- commonly used types
	immutable collection types Map, Set, and the List constructors
	tuples(scala tuple combines a **fixed** number of items together so that they can be passed around as a whole. unlike array or list, tuple can hold different types of objects with different types but they are also immutable)

- console I/O
	Predef provides a number of simple functions for console I/O, such as printf, println, readLine, readInt, and etc. These functions are all aliases provided by scala.Console

- Assertions
	A set of assert functions can be provided for use as a way to document and dynamically check invariants in code.

Variants of assert intended for use with static analysis tools are also provided: assert, require and ensuring. require and ensuring are intended for use as means of design-by-contract style specifictaion of of pre- and post-conditions on funcations, with the intention that these specifications could be consumed by a static analysis tool.

```Scala
 def addNaturals(nats: List[Int]): Int = {
   require(nats forall (_ >= 0), "List contains negative numbers")
   nats.foldLeft(0)(_ + _)
 } ensuring(_ >= 0)
```

 The declaration of addNaturals states that the list of integers passed should only contain natural numbers (i.e. non-negative), and that the result returned will also be natural. require is distinct from assert in that if the condition fails, then the caller of the function is to blame rather than a logical error having been made within addNaturals itself. ensures is a form of assert that declares the guarantee the function is providing with regards to it's return value.


**static analysis**

also called static code analysis, is a method of computer program debugging that is done by examining the code without executing the program. the process provides an understanding of the code structure, and can help to ensure that the code adheres to industry standards. Automated tools can assist programmers and developers in carrying out static analysis. The process of scrutinizing code by visual inspection alone(by looking at a printout, for exmample), without the assistance of the automated tools, is sometimes called program understanding or program comprehension.

logistic function


