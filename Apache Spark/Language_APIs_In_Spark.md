Spark’s Language APIs
-------

Apache Spark is one of the most popular framework for big data analysis released in 2010 by Berkeley's AMPLab. Spark is primarily written in Scala, making it Spark’s 
“default” language, but one of spark's selling point is the cross-language API that allows you to write Spark code in Scala, Java, Python or R. These programming 
languages are either compiled or interpreted. We will explain the difference between compiled and interpreted programming languages then we will move to define spark's programming languages. 


Compiled vs Interpreted Language
-------
The main goal of both compilation and interpretation is to transform the human-readable source code into machine code that can be executed directly by a CPU, but there are some caveats to it.

One of the main things we have to understand is that a programming language itself is neither compiled nor interpreted, but the implementation of a programming language is. In fact, there are many programming languages that have been implemented using both compilers and interpreters.


### Compiled Programming Language : 
A compiled language is a programming language which are generally compiled and not interpreted. A compiler is a program that translates statements written in a particular programming language into another language usually machine code. A standard compiler instead of translating code on the fly does all of its work ahead of execution time. It is one where the program, once compiled, is expressed in the instructions of the target machine; this machine code is undecipherable by humans. Types of compiled language – C, C++, C#, CLEO, COBOL, etc.

In C++ the source code is compiled into machine code. The compilation process consists of preprocessing, compiling and linking, but the end result is either a library or an executable that can be executed directly by a CPU that the program was compiled for.

##### Benefit of compiled languages: 
The speed of execution as the executable that contains machine code can be directly executed on the target machine without any additional steps.

##### Drawback of compiled languages: 
Poor portability as programs have to be compiled for a specific CPU architecture and a long time that is required for the actual compilation.


<p align="center">
  <img width="460" height="400" src="Img/compiled-interpreted.png">
</p>


### Interpreted Programming Language : 
An interpreted language is a programming language which are generally interpreted, without compiling a program into machine instructions. It is one where the instructions are not directly executed by the target machine, but instead read and executed by some other program. We can say that the interpreter translates programs on
the fly instead of focusing on the whole program at once. Interpreted language ranges – JavaScript, Perl, Python, BASIC, etc.

Even though interpreter could be translating source code into machine code, these days most of the interpreters work with an intermediate representation also called bytecode in most interpreted programming languages. This is because interpreting source code directly would be quite slow and most interpreted languages benefit from compiling into bytecode first that can prepare and optimise the code for further interpretation into machine code.
 
##### Benefit of interpreted languages: 
Portability as programs don’t have to be compiled for a specific CPU architecture and faster compilation process (for the language implementations that compile to bytecode).

##### Drawback of interpreted languages: 
Slower execution speed and potential for leaking source code if the non-obfuscated source code is sent to the client.



Spark’s Programming Language 
-------

### Scala : 
Scala is a highly Scalable Language and a crossover between object-oriented and functional programming language. Scala was invented by the German Computer Scientist, 
Martin Odersky and the first version was launched in the year 2003.  It runs on JVM (Java Virtual Machine) and interoperates with existing Java code and libraries.
In Scala you need to compile your code, which creates a file that contains bytecode that is executed in the Java Virtual Machine. Since Scala runs on top of the JVM, it means that you can leverage existing Java libraries which greatly increases available functionality. So, when you need to make a small change, you can’t just open the source code with a text editor, make a change and re-execute. You need to compile using scalac (for example) and then execute.
Scala is the native language of Spark. It means any new API always first be available in Scala. It is also the only language that supports the typed Dataset functionality and, along with Java, allows one to write proper UDAFs (User Defined Aggregation Functions).

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
Python is an interpreted language and one of the de-facto languages of Data Science and as a result a lot of effort has gone into making Spark work seamlessly with Python despite being on the JVM. In Python, in the reference implementation you execute .py files which contain source code that gets compiled into bytecode and then executed. So, there is a compilation step, but you can always open the source with vi or any other text editor, make a change and execute again with that change. That’s why Python is seen as an interpreted language, and can be fairly convenient when coding. 

Since Spark 2.3 there is experimental support for Vectorized UDFs which leverage Apache Arrow to increase the performance of UDFs written in Python. As a note, Vectorized UDFs have many limitations including what types can be returned and the potential for out of memory errors.

##### Advantages of Python: 
- It is interpreted language (i.e. support to REPL, Read, Evaluate, Print, Loop.) If you type a command into a command-line interpreter and it responds immediately. Java lacks this feature.
- Easy to learn, easy debugging, fewer lines of code.
- It is dynamically typed. i.e. can dynamically defined variable types. i.e. Python as a language is type-safe.
- Python is platform agnostic and scalable.

##### Downsides of Python:
- Python is slow. Big data professionals find projects built in Java / Scala are faster and robust than the once with python.
- Python does not support heavy weight processing


### R : 
R is the language of statistics. R is a language and environment for statistical computing and graphics. R was created by Ross Ihaka and Robert Gentleman at the University of Auckland, New Zealand, and is currently developed by the R Development Core Team. Spark has two commonly used R libraries: one as a part of Spark core (SparkR) and another as an R community-driven package (sparklyr).

##### Advantages of R: 
- Strong statistical modeling and visualization capabilities.
- Support for ‘data science’ related work.
- It can be integrated with Apache Hadoop and Spark easily.

##### Downsides of R:
- R is not a general-purpose language.
- The code written in R cannot be directly deployed into production. It needs conversion into Java or Python.
- Not as fast as Java / Scala.


### JAVA : 
Java is one of the oldest languages of all programming languages listed previously. Traditional Frameworks of Big data like Apache Hadoop and all the tools within its ecosystem are Java-based and hence using java opens up the possibility of utilizing large ecosystem of tools in the big data world. Even though Spark is written in Scala, Spark’s authors have been careful to ensure that you can write Spark code in Java. 

##### Advantages of JAVA: 
- Java is platform-agnostic language and hence it can run on almost any system. Java is portable due to something called Java Virtual Machine – JVM. JVM is a foundation of Hadoop ecosystem tools like Map Reduce, Storm, Spark, etc. These tools are written in Java and run on JVM.
- Java provides various communities support like GitHub and stack overflow etc.
- Java is scalable, backward compatible, stable and production-ready language. Also, supports a large variety of tried and tested libraries.
- It is statically typed language (We would see details of this functionality in later sections, in comparison with others)

##### Downsides of JAVA:
- Java does not support Read-Evaluate-Print-Loop (REPL) which is a major deal-breaker when choosing a programming language for big data processing.
- You need to write long code to achieve simple functionality in Java.
- Lack of machine learning languages.


Comparison of four languages for Apache Spark
-------
Links below contains a deep comparaison between the 4 languages definied previously for Apache Spark : 
- https://www.knowledgehut.com/blog/programming/scala-vs-python-vs-r-vs-java
- https://mindfulmachines.io/blog/2018/6/apache-spark-scala-vs-java-v-python-vs-r-vs-sql26

