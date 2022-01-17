How to create RDD : 
---------
### Using sparkContext.parallelize() : 
Used to parallelize an existing collection in the driver program.
```scala
//Create RDD from parallelize    
val dataSeq = Seq(("Java", 20000), ("Python", 100000), ("Scala", 3000))   
val rdd=spark.sparkContext.parallelize(dataSeq)
```
For production applications, we mostly create RDD by using external storage systems like HDFS, S3, HBase etc.

### Using sparkContext.textFile():
Using textFile() method to read txt file.
```scala
val rdd2 = spark.sparkContext.textFile("/path/textFile.txt")
```

### Using sparkContext.wholeTextFiles():
The function wholeTextFiles() function returns a PairRDD with the key being the file path and value being file content.
```scala 
//Reads entire file into a RDD as single record.
val rdd3 = spark.sparkContext.wholeTextFiles("/path/textFile.txt")
```
### Using sparkContext.emptyRDD:
Using emptyRDD() method on sparkContext we can create an RDD with no data. This method creates an empty RDD with no partition.
```scala 
//Creates empty RDD with no partition    
val rdd = spark.sparkContext.emptyRDD // creates EmptyRDD[0]
val rddString = spark.sparkContext.emptyRDD[String] // creates EmptyRDD[1]
```

### Creating empty RDD with partition:
```scala 
//Create empty RDD with partition
val rdd2 = spark.sparkContext.parallelize(Seq.empty[String])
```

RDD Parallelize and repartition :
----------
### Get number of partitions:
When we use parallelize() or textFile() or wholeTextFiles() methods of SparkContxt to initiate RDD, it automatically splits the data into partitions based on resource availability.
The function getNumPartitions returns the number of partitions.
```scala 
println("initial partition count:"+rdd.getNumPartitions)
//Outputs: initial partition count:2
```
### How choose number of partitions : 
We can choose the number of partition (example number of partitions = 10) : 
```scala
sparkContext.parallelize(dataSeq, 10))
```
### Repalallize using repartition and coalesce :
Some times we may need to repartition the RDD, Spark provides two ways to repartition:
- repartition : method which shuffles data from all nodes also called full shuffle. It is a very expensive operation as it shuffles data from all nodes in a cluster. 
- coalesce : method which shuffle data from minimum nodes, for examples if you have data in 4 partitions and doing coalesce(2) moves data from just 2 nodes.  
```scala
val reparRdd = rdd.repartition(4)
println("re-partition count:"+reparRdd.getNumPartitions)
//Outputs: "re-partition count:4
```

RDD Transformations : 
------------
### flatMap():
It flattens the RDD after applying the function and returns a new RDD.
```scala
val rdd2 = rdd.flatMap(f=>f.split(" "))
```

### map():
It is used the apply any complex operations like adding a column, updating a column e.t.c, the output of map transformations would always have the same number of records as input.
```scala
val rdd3:RDD[(String,Int)]= rdd2.map(m=>(m,1))
```

### filter():
```scala
//Filtering a word which start with "a"
val rdd4 = rdd3.filter(a=> a._1.startsWith("a"))
```

### reduceByKey():
It merges the values for each key with the function specified. 
```scala
val rdd5 = rdd4.reduceByKey(_ + _)
```
### sortByKey():
To sort RDD elements on key.
```scala
//Convert RDD[(String,Int]) to RDD[(Int, String]) using map transformation and apply sortByKey which ideally does sort on an integer value.
val rdd6 = rdd5.map(a=>(a._2,a._1)).sortByKey()
//Print rdd6 result to console
rdd6.foreach(println)
```

RDD Actions : 
------------
### count():
```scala
\\Returns the number of records in an RDD
println("Count : "+rdd6.count())
```

### first():
```scala
val firstRec = rdd6.first()
println("First Record : "+firstRec._1 + ","+ firstRec._2)
```

### max(): 
```scala
val datMax = rdd6.max()
println("Max Record : "+datMax._1 + ","+ datMax._2)
```

### reduce():
```scala
val totalWordCount = rdd6.reduce((a,b) => (a._1+b._1,a._2))
println("dataReduce Record : "+totalWordCount._1)
```

### take():
```scala
val data3 = rdd6.take(3)
data3.foreach(f=>{
    println("data3 Key:"+ f._1 +", Value:"+f._2)
})
```
### collect():
Returns all data from RDD as an array. Be careful when you use this action when you are working with huge RDD with millions and billions of data as you may run out of memory on the driver.
```scala
val data = rdd6.collect()
data.foreach(f=>{
   println("Key:"+ f._1 +", Value:"+f._2)
})
```

### saveAsTextFile():
````scala
rdd6.saveAsTextFile("/tmp/wordCount")
```



