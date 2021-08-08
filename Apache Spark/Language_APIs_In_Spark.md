Spark’s Language APIs
-------

Apache Spark is one of the most popular framework for big data analysis released in 2010 by Berkeley's AMPLab. Spark is primarily written in Scala, making it Spark’s 
“default” language, but one of spark's selling point is the cross-language API that allows you to write Spark code in Scala, Java, Python, R or SQL. 


### Scala : 
Scala is a highly Scalable Language and a crossover between object-oriented and functional programming language. Scala was invented by the German Computer Scientist, 
Martin Odersky and the first version was launched in the year 2003.  It runs on JVM (Java Virtual Machine) and interoperates with existing Java code and libraries.
Scala is the native language of Spark. It means any new API always first be available in Scala. It is also the only language that supports the typed Dataset functionality 
and, along with Java, allows one to write proper UDAFs (User Defined Aggregation Functions).

##### Advantages of Scala: 
- Scala is fast. It uses Java Virtual Machine (JVM) during runtime which gives is some speed over Python in most cases (Frequently over 10 times faster than Python).
Compiled languages are faster than interpreted. In case of Python, Spark libraries are called which require a lot of code processing and hence slower performance. In this scenario Scala works well for limited cores. Moreover Scala is native for Hadoop as its based on JVM. Hadoop is important because Spark was made on the top of the Hadoop's filesystem HDFS. Python interacts with Hadoop services very badly, so developers have to use 3rd party libraries (like hadoopy). Scala interacts with Hadoop via native Hadoop's API in Java. That's why it's very easy to write native Hadoop applications in Scala.
- One complex line of Scala code replaces between 20 to 25 lines of Java code. There is robust interoperability between Scala and Java code. Scala developers can also use their Scala code to access Java libraries directly.
- Scala handles concurrency and parallelism very well, while Python doesn’t support true multi-threading. Due to its concurrency feature, Scala allows better memory management and data processing. However Python does support heavyweight process forking. 
- Scala is best suited for large-scale projects, while Python works better for small projects.
- Scala is a statically typed language which allows us to find compile time errors. whereas Python is a dynamically typed language. Python language is highly prone to bugs every time you make changes to the existing code. Hence refactoring the code for Scala is easier than refactoring for Python.

 ##### Downsides of Scala:
- Scala is complex to learn due to the functional nature of language.
- Scala is more complex, compared to Python. The latter’s syntax and standard libraries contribute much to the language’s simplicity.
- Lack of matured machine learning languages (GraphX, GraphFrames and MLLib). 

### Python : 

