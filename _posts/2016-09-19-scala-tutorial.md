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

This online tutorial gives us a comprehensive introduction of Scala's syntax and difference from Java. The following is my summary of this interesting tutorial.

---

# Begin with Hello World!

```scala
object HelloWorld {
  def main(args: Array[String]) {
    println("Hello, world!")
  }
}
```

>The structure of the program is quite simple: it consists of one method called **main** which takes the command line arguments, an array of strings, as parameters; the body of this method consists of a single call to the pre-defined method **println** with the friendly greeting as argument. [^1]

## Some casual comparisons to other programming languages:

* Python

	----

	Scala defines a method using key word **def** just like Python but you still need to specify the types of all the arguments in a format: ***(Variale: Type, Variale: Type,  ...)***. Scala also gets rid of semicolons like Python but still keeps curly braces to confine a block of codes under the same control. 
* Java
	
	----

	**Less familiar to Java programmers**:

	>The **object** declaration containing the ***main*** method. Such a declaration introduces what is commongly known as a *singleton* object, that is a class with a single instance. The declaration above thus declares both a class called *HelloWorld* and an instance of that class, also called *HelloWorld*. This instance is created on demand, the first time it is used.[^2]

	>The ***main*** method is not declared as *static* here. **This is because static members(methods or fields) do not exist in Scala**. Rather than defining static members, the Scala programmer declares these members in singleton objects.

	 **Similarity**:

	process of Scala is quite similar to that of Java. The Scala compiler is named as *scalac*, so scalac as for(with regard to) scala is just like javac as for java. Scalac takes a source file as an argument, maybe some options, and produces one or several object files. **The object files it produces are standard Java class files.**


	
	  scalac HelloWorld.scala
	

	This will generate a few class files in the current directory. One of them will be called HelloWorld.class, and contains a class which can be directly executed using the scala command, as the following sction shows:

	
	  scalac -classpath . HelloWorld
	

	Output:
	  
	  Hello, world!
	

	<img src="{{sites.url}}/images/thinking_emoji.jpg" width="20" heihgt="20" align="left">


	Sometimes, we just forgot the simple happiness back to the original time when witnessing this single line of output. This inspirational surprise is fading away when growing up. As human, we somehow need to remind us of being "naive" to let this kind of simple joy shed light into our hearts. brevity is important to me.

	**Interaction With Java**:

	Scala interoperates seemlessly with Java so there is no need to implement equivalent classes in the Scala class library-we can simply import the classes of the responding Java packages.
	All classes from the java.lang package are imported by default, while others need to be imported explicitly.

	when importing all the names of a package or class, one uses the underscore character (_) instead of the asterisk (*). That’s because the asterisk is a valid Scala identifier

	Methods taking one argument can be used with an infix syntax. That is, the expression 

	  df format now

	is equal to 

	  df.format(now)
	This might seem like a minor syntactic detail, but it has important consequences. */_ or infix syntax will be explained in further section.

	** Everything is an object **

	Scala is a pure object-oriented language in the sense that *eveything* is an object, including numbers and functions. It differs from Java in that respect, since java






[^1]: I quote this piece of words from the tutorial since I have never thought of a good way to describe a hello world program. I guess this is a good one. Interesting words: structure, consists, as parameters, body of the method, call to predefined method. Also, this is a test for footnote feature in Markdown. And can anyone tell me a propriate way to write footnote? Can it be casually verbose like this?



