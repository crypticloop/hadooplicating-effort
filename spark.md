Spark
=====

## Overview

* 'Fast and general engine for large-scale data processing'
* Rich ecosystem of data for things such as:
  * Machine Learning
  * Graph analysis

* Spark can be its one cluster manager
  * Doesn't need to run on Hadoop

* **Spark is a memory based solution**
  * As opposed to a disk space solution
* It attempts to store as much as possible in the cache, i.e. ram, of the cluster machines
* Makes it very fast
  * 100x over MapReduce on RAM
  * 10x over MapReduce on disk
* Speed also attributed directed acyclic graphs
* Takes care of cluster organisation

* Spark can work backwards from the thing that you want to figure out the quickest way to get there

* Built around **Resilient Distributed Dataset (RDD)**
  * RDDs transformed by code packages
* Can code in Python, Java or Scala

* Spark also has components built on top of the core
  * Spark streaming - dealing with real-time information flow
  * Spark SQL - SQL interface to Spark
  * MLLib - machine learning and data mining
  * GraphX - graph theory analysis

* Spark itself is written in Scala
* Good functional programming
* Fast - compiles to Java Bytecode
  * Python is slow in comparison

## RDDs

* Resilient, distributed dataset
  * Created by driver program as a SparkContext
* Can run spark shell to create an 'sc' object, e.g.

`sc.textFile("...")`

* Can create an RDD from many different types of inputs
* Can run various operations on an RDD to transform it:
  * map (one to one)
  * flatmap (many to one)
  * filter
  * distinct
  * union

* In python, a simple RDD can be called with:

`rdd = sc.parallelize([1,2,3,4])`

* Can then square this using a lambda function:

`squaredRDD = rdd.map(lambda x: x*x)`

* This is an example of functional programming, defining functions inline

* There are also methods that interface with the RDD and return an object in your chosen language e.g. python:
  * collect
  * count
  * countByValue
  * reduce
* Nothing actually happens on your driver until one of these actions is called
* It then works backwards and figures out the quickest way to do this all
* Library is called `pyspark`:

`From pyspark import SparkConf, SparkContext`
