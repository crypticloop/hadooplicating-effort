Spark
=====

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
