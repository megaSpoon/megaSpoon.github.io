---
layout: post
title: Daily Report - 10/23
description: "daily report -- record what I learned today"
modified: 2016-10-23
tags: [daily log, ]
image:
  feature: Lascaux/Lascaux_II.jpg
  credit: Lascaux
  creditlink: https://en.wikipedia.org/wiki/Lascaux
---

Under the hood:
<hr>
The underlying implementation of a product implies that the implementation is not intuitively obvious from the apprearance,but the speaker is about to enable the listeners to grok it.

We can define RDDs any time we want, but Spark computes them only in a ***lazy fashion*** -- that is, the first time we used in an action. Explanation: This approach might seem unusual first, but makes a lot of sense when you are working with Big Data. Explanation: Save storage space and computing time. Once Spark sees the whole chain of transformations, it can compute just the data needed for its result.

unused but learned:

If you would like to reuse an RDD in ***multiple*** actions, you can ask Spark to persist it using RDD.persist(). We can ask Spark to persist our data in a number of persist using RDD.persist().

workflow,work as follows:

1. Create some input RDDs from external data
2. Transform them to define new RDDs using transformations like filter()
3. Ask Spark to persist() any intermmediate RDDs that will need to be reused
4. Launch actions such as count() and first() to kick off a parallel computation, which is then optimized and executed by Spark.

two way to create RDD:

- load data from external dataset
- parallelize a collection


To decide whether a given function is a transformation or an action, you can look at its return type: transformations return RDDs, whereas actiosn return some other data type.

use take( ) to retrieve a small amount of elements from the RDD.

use collect() to retrieve the entire RDD. It is useful when the RDD is downsized to a small one and you want to deal with it locally. Keep in mind that your entire dataset must fit in memory on a single machine.

In most cases, the RDDs are just too large to be collecte()d to the drive. Then it's common to write these data out to a distributed stoage system such as HDFS or Amazon S3. You can save the contents of an RDD using the saveAsFiles() action, saveAsSequenceFile(), or any of a member of actiosn for various built-in formats. 

It's important to note that each time we call a new action, the entire RDD must be computed "from scratch". To avoid this efficiency, users can persist intermediate results.

lazy evalation: Spark will not begin to execute until it sees an action.

Serializable:
To serialize an object means to convert its state to a byte stream so that the byte stream can be reverted back into a copy of the object.