---
layout: post
title: Daily Report - 10/24
description: "daily report -- record what I learned today"
modified: 2016-10-21
tags: [daily log, ]
image:
  feature: TheKnightAtTheCrossroads.jpg
  credit: Vasnetsov
  creditlink: https://en.wikipedia.org/wiki/Viktor_Vasnetsov
---

a val must have assigned an initial value, in your case as a local value in a method body.

a val on an abstract class or trait may be left un-initialized - though it must be initialized by a (concrete) subclass somewhere along the line,