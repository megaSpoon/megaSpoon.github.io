---
layout: post
title: Daily Report - 11/07
description: "daily report -- record what I learned today"
modified: 2016-11-01
tags: [daily log, ]
image:
  feature: colorful-dog.jpg

---

Q: Is it possible to convert machine code back to a programming language?

A: Decompilers, which do exactly what you’re asking for, have been around for decades. But you won’t get what you might expect out of them: source code which is easily readable for human programmers. Details like meaningful variable, function, or class names are lost in the process, and of course so are comments. The structure might not resemble the original source code either because modern compilers go through several rounds of optimization before they create the final binary version of a program.

Q: What is the advantage of using abstract classes instead of traits?
A: Whenever you implement a reusable collection of behavior, you will have to decide whether you want to use a trait or an abstract class. There is no firm rule, but this section contains a few guidelines to consider.

If the behavior will not be reused, then make it a concrete class. It is not reusable behavior after all.

If it might be reused in multiple, unrelated classes, make it a trait. Only traits can be mixed into different parts of the class hierarchy.

If you want to inherit from it in Java code, use an abstract class. Since traits with code do not have a close Java analog, it tends to be awkward to inherit from a trait in a Java class. Inheriting from a Scala class, meanwhile, is exactly like inheriting from a Java class. As one exception, a Scala trait with only abstract members translates directly to a Java interface, so you should feel free to define such traits even if you expect Java code to inherit from it. See Chapter 29 for more information on working with Java and Scala together.

If you plan to distribute it in compiled form, and you expect outside groups to write classes inheriting from it, you might lean towards using an abstract class. The issue is that when a trait gains or loses a member, any classes that inherit from it must be recompiled, even if they have not changed. If outside clients will only call into the behavior, instead of inheriting from it, then using a trait is fine.

If efficiency is very important, lean towards using a class. Most Java runtimes make a virtual method invocation of a class member a faster operation than an interface method invocation. Traits get compiled to interfaces and therefore may pay a slight performance overhead. However, you should make this choice only if you know that the trait in question constitutes a performance bottleneck and have evidence that using a class instead actually solves the problem.

If you still do not know, after considering the above, then start by making it as a trait. You can always change it later, and in general using a trait keeps more options open.

## Upper Type Bounds

An upper type bound T <: A declares that type variable T refers to a subtype of type A

When used as parameter bounds, the statement of the function should look like: 

```scala
object UpperBoundTest extends App {
  def findSimilar[T <: Similar](e: T, xs: List[T]): Boolean =
    if (xs.isEmpty) false
    else if (e.isSimilar(xs.head)) true
    else findSimilar[T](e, xs.tail)
  val list: List[MyInt] = List(MyInt(1), MyInt(2), MyInt(3))
  println(findSimilar[MyInt](MyInt(4), list))
  println(findSimilar[MyInt](MyInt(2), list))
}
```

Q: What is Condition Number?
A: If the condition number is very large, then the matrix is said to be ill-conditioned. Practically, such a matrix is almost singular, and the computation of its inverse, or solution of a linear system of equations is prone to large numerical errors.

Scaling the variables often reduces this condition number in the columns.

	logisticRegressionModel

	extends GeneralizedLinearModel

	- validators
	- two variable: isAddIntercept / useFeatureScaling
	- createModel
	- run 
		\- scale the features to reduce conditional number of the matrix
		\- create the model