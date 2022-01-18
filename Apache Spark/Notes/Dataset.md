How to create Dataset
-----------------------

### Create sample data
```scala
// range of 100 numbers to create a Dataset.
val range100 = spark.range(100)
range100.collect()
```

### Load from existing file
```scala
// First, define a case class that represents a type-specific Scala JVM Object
case class Person (name: String, age: Long)
// Read the JSON file, convert the DataFrames into a type-specific JVM Scala object
// Person. At this stage Spark, upon reading JSON, created a generic
// DataFrame = Dataset[Rows]. By explicitly converting DataFrame into Dataset
// results in a type-specific rows or collection of objects of type Person
val ds = spark.read.json("/samples/people/people.json").as[Person]
```
There are two reasons to convert a DataFrame into a type-specific JVM object:
- After an explicit conversion, for all relational and query expressions using Dataset API, you get compile-type safety. For example, if you use a filter operation using the wrong
data type, Spark detects mismatch types and issues a compile error rather an execution runtime error, so that you catch errors earlier. 
- The Dataset API provides high-order methods, which makes code much easier to read and develop. In the section Process and visualize the Dataset, notice how using Dataset 
typed objects makes the code easier to express and read.

View the Dataset
-------------
```scala
// display the dataset table just read in from the JSON file
display(ds)
// Using the standard Spark commands, take() and foreach(), print the first
// 10 rows of the Datasets.
ds.take(10).foreach(println(_))
```
