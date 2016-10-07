---
layout: post
title: class schedule
description: "self-learning challenge"
modified: 2016-09-28
tags: [daily log, english, vocabulary, MOOC, MIT Challenge]
image:
  feature: 
link: https://courses.edx.org/courses/course-v1:MITx+6.005.1x+3T2016/courseware/Readings_Videos/02-Code-Review/
---
- rubrics
- be embarking on this experiment
- cramming
- retension
- forgo
- silver board
- split off and break the rule

- build the consistency
- active learning
- critical thinking
- retention
- flesh them out into actual mode
- consider each comment independently as if the other comments weren't there.
- specification, clarifies what it means and what those numbers signify
- zero-based indexing for months.
- for historical reason

# Outline:
## avoid repeating yourself

## Write Comment

## fail fast

## avoid magic numbers

## Three rules of coding
## Don't reuse 
## Use good names

## Use whitespaces to help 
## DON'T USE 

---

# Note:

what do you have?  -- knowledge
which of these do you choose? -- experience

## avoid repeating yourself
Loop statements like for and while are both good approaches to condensing your repretitive code.

A switch statement is a more compact way to represent a series of if-else-if statements. it does help DRY the code out by eliminating the repretitive mentions of the conditions, but it won't reduce the repetitions of the opertations.

Recursive functions can also be a very effective way to reduce the amount of the codes. You could transform an iteration into recursive function easily by specifying the base case and handles other cases by recursion.

## Write Comment

Commets make the codes easier to undestand.

The kinds of comment:
- crucial one:
	speicification which appears above a method or a class and documents the behavior of the method or class. In Java, this is conventionally written as a Javadoc comment, meaning that it stats with /** and includes @-syntax, like @param and @return for methods. Here is an example of a spec:

	```
	/**
 	* Compute the hailstone sequence.
 	* See http://en.wikipedia.org/wiki/<Collatz_conjecture id="Stat"></Collatz_conjecture>ement_of_the_problem
 	* @param n starting number of sequence; requires n > 0.
 	* @return the hailstone sequence starting at n and ending with 1.
 	*         For example, hailstone(3)=[3,10,5,16,8,4,2,1].
 	*/
 	```

public static List<Integer> hailstoneSequence(int n) {
...
}
- saying where the code comes from helping us avoid violatins of copyright.

## fail fast
 helps reveal the bug that could corrupt subsequent computation as quickly as possible.

 ```
 public static int dayOfYear(int month, int dayOfMonth, int year) {
    if (month == 2) {
        ...
    } else if (month == 12) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31 + 30 + 31 + 31 + 30 + 31 + 31;
    }
    return dayOfMonth;
}
```

The dayOfYear function doesn't fail fast -- if you pass it the arguments in the wrong order, it will quietly return the wrong answer. In fact, the way dayOfYear is desgined, it's high likely that a non-American will pass the arguments in the wrong order! It needs more checking -- either static checking and dynamic checking.

Kinds:
- static checking
- dynamic checking

## avoid magic numbers
There are really only three constants that computer scientists recognize as valid in and of themselves: 0 and 1, and maybe 2.(Okay, three constants)

All other constants are called magic, because they appear as if out of thin air with no explanation. One way to explain a number is with a comment, but a far better way is to declasre the number as named constant with a good, clear name.

dayOfYear is full of magic numbers:

The months 2, …, 12 would be far more readable as FEBRUARY, …, DECEMBER.
The days-of-months 30, 31, 28 would be more readable (and eliminate duplicate code) if they were in a data structure like an array, list, or map, e.g. MONTH_LENGTH[month].

The mysterious numbers 59 and 90 are particularly pernicious examples of magic numbers. Not only are they uncommented and undocumented, but they are also the result of a computation done by hand by the programmer. Don't hardcode constants that you've computed by hand. Java is better at arithmetic than you are. 

Explicit computations like 31 + 28 make the provenance of these mysterious numbers much clearer. MONTH_LENGTH[JANUARY] + MONTH_LENGTH[FEBRUARY] would be clearer still.

## Three rules of coding
- SFB: safe from bugs
	checking(corner cases)
- ETU: easy to understand
	comment, name the magic numbers, data structure
- RFC: ready to change
	data structure to store the data

## Don't reuse parameters, and don't reuse variables. 

Variables are not a scarce resource in programming. Introduce them freely, give them good names, and just stop using them when you stop needing them. 

It's a good idea to use final for method parameters, and as many other variables as you can. 
## Use good names
In Java:
- methodAreNamedWithCamelCaseLikeThis
- variablesAreAlsoCamelCase
- CONSTANTS_ARE_IN_ALL_CAPS_WITH_UNDERSCORES
- ClassesAreCapitalized
- packages.are.lowercase.and.seperated.by.dots

## Use whitespaces to help the reader
Never use tab characters, only space characters. Note that we say characters, not keys. We are not saying you should never press the TabKey, only that your editor should never put a tab character into your source file in response to your pressing the TabKey. The reason for this is that different tools treat tab characters differently.

Mixing spaces and tabs can result in code that is hard to understand, and not safe from bugs either, because other programmers maintaining it may misunderstand the block structure and put new code in the wrong place.

## DON'T USE GLOBAL VARIABLES

In Java, a global variable is declared public static. The public modifier makes it accessible anywhere, and static means there is a single instance of the variable.

In general, change global variables into parameters and return values, or put them inside objects that you're calling methods on. We'll see many techniques for doing that in future readings.

## METHODS SHOULD RETURN RESULTS, NOT PRINT THEM

In general, only the highest-level parts of a program should interact with the human user or the console.

The sole exception here is debugging output, which can of course be printed to the console. But that kind of output shouldn't be a part of your design, only a part of how you debug your design.

---

n % 2 == 0 is an expression, which means a part of the program that generates a value. In this case, the value is a boolean value, either true or false, which is then used by the if statement to decide which part of the program to run next.

n is a variable, % and == are operators, and the if block is a statement.

Integer overflows quietly produce the wrong answer.

Division by zero can't produce a real number either -- but unlike real numbers, double has a special value for POSITIVE_INFINITY, so that's what it returns when you divide a positive integer by zero. If the code is trying to compute an average value, infinity is unlikely to be a correct or useful answer.

Why do we need to write down our assumptions? Because programming is full of assumptions. If we don't write them down, we won't remember them, and other people who need to read or change our programs later won't know them. They'll have to guess.

Programs have to be written with two goals in mind:

- communicating with the computer. 	First persuading the compiler that your program is sensible — syntactically correct and type-correct — and then getting the logic right so that it gives the right results at runtime.
- communicating with other people. Making the program easy to understand, so that when somebody has to fix it, improve it, or adapt it in the future, they can do so.