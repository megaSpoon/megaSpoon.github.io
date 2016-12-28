---
layout: post
title: Scala 
decription: "get the whole project fixed by myself"
modified: 2016-10-10
image:
   feature:

---

# Scala:

## String Interpolation

[link](http://docs.scala-lang.org/overviews/core/string-interpolation.html)

String interpolation allows users to embed varaible references directly in processed string literals. 

Example:

```Scala
val name = "Bowen"
println(s"Hellow, $name")
```

## s

In the above, the literal s "Hello, $name" is a processed string literal. This means that the compiler does some additional work to this literal. A processed string literal is denoted by a set of characters preceding the ".

## f

Prepending f to any string literal allows the creation of simple formatted strings, similar to printf in other languages. When using the f interpolator, all variable references should be followed by a pritf-style format string, like %d.

## raw

The raw interpolator is similar to the s interpolator except that it performs no escaping of literals within the string.

