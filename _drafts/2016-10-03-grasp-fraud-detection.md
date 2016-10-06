---
layout: post
title: Scala Official Tutorial Summary
description: "scala"
modified: 2016-09-19
tags: [daily log, scala, summary]
image:
  feature: abstract-3.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
link: http://www.scala-lang.org/docu/files/ScalaTutorial.pdf
---

Project Structure:

fraud-detection
|-- .idea
	|-- copyright
		|-- profiles_settings.xml
	`-- other xml files
`-- out
	(I have no idea about what it is used to do)
`-- src
	|-- fraudDetection
		|-- application
			|-- SimpleApp
		`-- classification
			|-- Bagging.scala
		`-- feature
			`-- StraightfieldSampler.scala
			...
		`-- pipeline
		`-- util

---

This is a self-contained application using the Spark API. 

---
# Scala
In Scala, you need to specify the **type signature** for **function parameters**. The interpreter happily repeats the type signature back to you.

String*: multiple-String type
You can leave parens on functions with no arguments.

If your function is made up of many expressions, you can use {} to give yourself some breathing room.


You can partially apply a function with an underscore, which gives you another function. Scala uses the underscore to mean different things in different contexts, but you can usually think of it as an unnamed magical wildcard.

In mathematics and computer science, currying is the technique of translating the evaluation of a function that takes multiple arguments (or a tuple of arguments) into evaluating a sequence of functions, each with a single argument. Currying is related to, but not the same as partial application.	

Sometimes it makes sense to let people apply some arguments to your function now and others later.

Here’s an example of a function that lets you build multipliers of two numbers together. At one call site, you’ll decide which is the multiplier and at a later call site, you’ll choose a multiplicand.

```scala
    scala> val timesTwo = multiply(2) _
    timesTwo: (Int) => Int = <function1> 
    ## look out for the space between ')' and _
    scala> timesTwo(3)
    res1: Int = 6


Anonymous functions:

## FeaturesByCategory.scala
Features:
category
smallCategory
numerficFeatures
flag
time

