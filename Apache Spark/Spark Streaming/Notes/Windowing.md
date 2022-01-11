Aggregationg over longer time spans
--------------

#### Windowed transformations : 
- Allow you to compute results across a longuer time period than your batch interval
- For example to identify top sellers for the past hour we need : Process data every one second + Maintain a window of one hour

#### Batch Interval vs Slide Interval vs Window Interval : 
- The batch interval is how often data is captured into a DStream
- The slide interval is how often a windowed transformation is captured 
- The window interval is how for back in time the windowed transformation goes

#### Code : 
The batch interval is set up with SparkContext : 
```scala
val scc = new StreamingContext("local[*]","TopSellers",Seconds(1))
```

Use reduceByWindow() or reduceByKeyAndWindow() to aggregate data across a long period of time:
```scala
val topCounts = topKeyValues.reduceByKeyAndWindow((x,y)=> x+y,(x,y)=>x-y,Seconds(300),Seconds(1))
```
