Hive
====

* Makes cluster look like a MySQL database
* Translates SQL into MapReduce
  * Actual name is HiveQL
* Makes OLAP queries easier
  * On line analytics processing

* Do not issue loads of requests, as it is pretty slow
* Not a real database, so no transactions possible

## Views

* Can store the results of a query into a view
  * Is not real storage, is a logical construct
* Can then run more queries on top of this

## How Hive works

* Schema on read
  * Takes unstructured data, and imposes a schema onto it when it's read
* `LOAD` moves data into Hive
  * No reformatting taking place, just keeping the schema in it's metastore
* `LOCAL` moves local data into Hive
* If you create an external table, Hive doesn't take ownership of the data

* Partitioning allows you to store data in partitioned subdirectories
  * Increases efficiency greatly if queries only required on certain subdirectories
* Can store STRUCT data inside Hive as well

* Queries can be saved
* Can access Hive via Oozie
  * Oozie is management tool for scheduling more complicated jobs
