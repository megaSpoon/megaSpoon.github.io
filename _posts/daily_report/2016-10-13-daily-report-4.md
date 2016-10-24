---
layout: post
title: Daily Report - 10/13
description: "daily report -- record what I learned today"
modified: 2016-09-19
tags: [daily log, ]
image:
  feature: Vasnetsov_samolet.jpg
  credit: Victor Vasnetsov
  creditlink: https://en.wikipedia.org/wiki/Viktor_Vasnetsov

---
Log4j是Apache的一个开源项目，通过Log4j，我们可以记录程序运行时的出错信息，便于软件开发人员分析错误原因，修正Bug。Log4j也可以充当集成开发环境中的调试器的作用，向文件或控制台打印代码的调试信息。Log4j还可以监视程序运行的情况，周期性的记录到文件中或数据库中，以便日后进行统计分析。 

记录器的日志级别在org.apache.log4j.Level类中定义，一共有5种可能的级别，从低到高依次是DEBUG，INFO，WARN，ERROR和FATAL。如果一个记录器没有指定日志级别，那么它将从最近的一个指定了级别的祖先继承级别。 

---

Logging is an important component of the software development. A well-written logging code offers quick debugging, easy maintenance, and structured storage of an application's runtime information.

Logging does have its drawbacks also. It can slow down an application. If too verbose, it can cause scrolling blindness. To alleviate these concerns, log4j is designed to be reliable, fast and extensible.

Since logging is rarely the main focus of an application, the log4j API strives to be simple to understand and to use.

---

记录器的日志级别在org.apache.log4j.Level类中定义，一共有5种可能的级别，从低到高依次是DEBUG，INFO，WARN，ERROR和FATAL。如果一个记录器没有指定日志级别，那么它将从最近的一个指定了级别的祖先继承级别。 

---
[software development directory structure][https://www.iuliantabara.com/2013/12/what-is-your-software-development-directory-structure/]

In computer science, a library is a collection of implementations of behavior, written in terms of a language, that has a well-defined interface by which the behavior is invoked. 

软件（英语：software）是一系列按照特定顺序组织的电脑数据和指示，是电脑中的非有形部分。

一般来说，计算机软件划分为编程语言、系统软件、应用软件和介于这两者之间的中间件。

软件包括所有在电脑运行的程序，和其架构无关，例如可执行文件、库及脚本语言都属于软件。软件不分架构，有其共通的特性，在运行后可以让硬件运行依设计时要求的机能。软件存储在内存中，软件不是可以碰触到的实体，可以碰触到的都只是存储软件的零件（内存）或是媒介（光盘或磁片等）。

系统软件（英语：System software），主要指用来运行或控制硬件所开发的计算机软件，如操作系统、解释器、编译器、数据库管理系统、公用程序等面向开发者的软件。

中间件（英语：Middleware），又译中间件，是提供系统软件和应用软件之间连接的软件，以便于软件各部件之间的沟通，特别是应用软件对于系统软件的集中的逻辑
.

一般认为在商业中间件及信息化市场主要存在微软阵营、Java阵营、开源阵营。阵营的区分主要体现在对下层操作系统的选择以及对上层组件标准的制订。目前主流商业操作系统主要来自Unix、苹果公司和Linux的系统以及微软视窗系列。微软阵营的主要技术提供商来自微软及其商业伙伴，Java阵营则来自IBM、Sun（已被Oracle收购）、Oracle、BEA（已被Oracle收购）、金蝶（Kingdee Apusic）及其合作伙伴，开源阵营则主要来自诸如Apache，SourceForge等组织的共享代码.