---
layout: post
title: Daily Report - 10/24
description: "daily report -- record what I learned today"
modified: 2016-10-21
tags: [daily log, ]
image:
  feature: Lascaux/lascaux.jpg
  credit: Lascaux
  creditlink: https://en.wikipedia.org/wiki/Lascaux
---

a val must have assigned an initial value, in your case as a local value in a method body.

a val on an abstract class or trait may be left un-initialized - though it must be initialized by a (concrete) subclass somewhere along the line.

MKL:

#Build environment
https://software.intel.com/en-us/articles/setting-up-the-build-environment-for-using-intel-c-or-fortran-compilers

My PC system details:
OS: CentOS 7
Memory: 31.1 GiB
Processor: Intel® Core™ i7-6700 CPU @ 3.40GHz × 8
OS type: 64 bit
Graphics: Gallium 0.4 on llvmpipe (LLVM 3.6, 256 bits)
GNOME: Version 3.14.2
Disk: 982.3 GB

dayTask:
1. happily find out the reason why the .so file cannot be produced
2. gently make ALS run on the SEAL with patience 

./bin/spark-submit --master local[*] --driver-memory 2g --class com.intel.analytics.seal.ALSExample SEAL-1.0-SNAPSHOT-jar-with-dependencies.jar 

hadoop fs -put /home/mageSpoon/Documents/work/Solutions/SEAL/ml-latest/ratings.csv /user/mageSpoon/data/mllib/als/ratings.csv

intel caffe tool: compare data in layers
1)	Download caffe from repository
2)	Add a first line into makefile: CXXFLAGS += -DDETERMINISTIC
3)	Build caffe: make all test -j
4)	./build/tools/caffe collect -gpu=0 -model examples/cifar10/cifar10_full_sigmoid_train_test_bn.prototxt
5)	./build/tools/caffe compare -model examples/cifar10/cifar10_full_sigmoid_train_test_bn.prototxt
6)	Compile Source.cpp (attached)
7)	Execute that program.

spark built with MKL: runtime is 54.593380932s
spark built without MKL: 40.163034964s

Being too bad or being too good. The art of finding the balance in people's hearts is called management. 

[Octorber 31 Monday 12:16 pm] 
Q: How to auto-compile project before running?
A: compiler settings -> check "make project automatically"

when hitting the run button, not only the single program will be compiled but also the whole project.

act like it and dress up for the occasion.

ren shi yike you si xiang de wei cao

200 year plan