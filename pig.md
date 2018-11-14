Pig
====

* Provides a quicker way of executing MapReduce tasks
* MapReduce is old, and therefore complicated
* Pig was introduced to speed up this process
* Not slower than MapReduce, as it can run **on top of Tez**
* Sits on top of MapReduce and Tez
  * Scripts are run on top of Tez
  * Tex runs Directed Acyclic Graph

* Can run from:
  * Grunt - one line at a time execution
  * Script
  * Ambari

* Example of Pig script:

`ratings = LOAD '/user/maria_dev/ml-100k/u.data' AS (userID:int, movieID:int, rating:int, ratingTime:int);`

* Schema is read in when you run the script
  * `ratings` has the schema written into it
* Then need to load the `u.item` file

`metadata = LOAD 'user/maria_dev/ml-100k/u.item' USING PigStorage('|') AS (movieID:int, movieTitle:chararry, releaseDate:chararray, videoRelease:chararray, imdbLink:charArray);

DUMP metadata;`

* DUMP is a print function, to show entries into this schema row by row
* Then make something a bit more usable and readable

`nameLookup = FOREACH metadata GENERATE movieID, movieTitle, ToUnixTime(ToDate(releaseDate, 'dd-MM-yyyy')) AS releaseTime;`

* Then group to create a 'bag', which is very similar to a 'reduce' operation

`ratingsByMovie = GROUP ratings BY movieID;`

* Finally, average the ratings across each set of values:

`avgRatigns = FOREACH ratingsByMovie GENERATE group AS movieID, AVG(ratings.rating) AS avgRating`

* This returns a set of results, in `([movieID],averageRating)` format
* Can now also `JOIN` tables by a certain variable
* Can also `ORDER ... BY ...`
