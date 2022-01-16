How to create RDD : 
---------
#### Using sparkContext.parallelize() : 
Used to parallelize an existing collection in the driver program.
```scala
//Create RDD from parallelize    
val dataSeq = Seq(("Java", 20000), ("Python", 100000), ("Scala", 3000))   
val rdd=spark.sparkContext.parallelize(dataSeq)
```
For production applications, we mostly create RDD by using external storage systems like HDFS, S3, HBase etc.

#### Using sparkContext.textFile():
Using textFile() method to read txt file.
```scala
val rdd2 = spark.sparkContext.textFile("/path/textFile.txt")
```

#### Using sparkContext.wholeTextFiles():
The function wholeTextFiles() function returns a PairRDD with the key being the file path and value being file content.
```scala 
//Reads entire file into a RDD as single record.
val rdd3 = spark.sparkContext.wholeTextFiles("/path/textFile.txt")
```
#### Using sparkContext.emptyRDD:
Using emptyRDD() method on sparkContext we can create an RDD with no data. This method creates an empty RDD with no partition.
```scala 
//Creates empty RDD with no partition    
val rdd = spark.sparkContext.emptyRDD // creates EmptyRDD[0]
val rddString = spark.sparkContext.emptyRDD[String] // creates EmptyRDD[1]
```

#### Creating empty RDD with partition:
```scala 
//Create empty RDD with partition
val rdd2 = spark.sparkContext.parallelize(Seq.empty[String])
```

RDD Parallelize and repartition :
----------
#### Get number of partitions:
When we use parallelize() or textFile() or wholeTextFiles() methods of SparkContxt to initiate RDD, it automatically splits the data into partitions based on resource availability.
The function getNumPartitions returns the number of partitions.
```scala 
println("initial partition count:"+rdd.getNumPartitions)
//Outputs: initial partition count:2
```
#### How choose number of partitions : 
We can choose the number of partition (example number of partitions = 10) : 
```scala
sparkContext.parallelize(dataSeq, 10))
```
#### Repalallize using repartition and coalesce :







