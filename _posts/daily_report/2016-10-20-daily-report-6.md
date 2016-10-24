	---
layout: post
title: Daily Report - 10/20
description: "daily report -- record what I learned today"
modified: 2016-10-20
tags: [daily log, ]
image:
  feature: TheKnightAtTheCrossroads.jpg
  credit: Vasnetsov
  creditlink: https://en.wikipedia.org/wiki/Viktor_Vasnetsov

---

Scope of Protection

Access modifier in Scala can be augumented with qualifiers. A modifier of the form private[X] or protected[X] means that access is private or protected "up to" X, where X designates some enclosing package, class or singleton object.

```scala
package society {
   package professional {
      class Executive {
         private[professional] var workDetails = null
         private[society] var friends = null
         private[this] var secrets = null

         def help(another : Executive) {
            println(another.workDetails)
            println(another.secrets) //ERROR
         }
      }
   }
}

```

Note − the following points from the above example −

- Variable workDetails will be accessible to any class within the enclosing package professional.

- Variable friends will be accessible to any class within the enclosing package society.

- Variable secrets will be accessible only on the implicit object within instance methods (this).



[a good article talking about a progammer's gists][http://www.hifreud.com/2015/03/11/let-it-go/#section]

when importing scala code, I must go to compile those codes first and turn them into scala class file composd of java bytecodes to be executed on JVM.

Q: How to create a jar file containing all the files under the specified dir?

A: jar cf jar-file-name.jar output-dir-path

	c : create f: specify the jar file name
