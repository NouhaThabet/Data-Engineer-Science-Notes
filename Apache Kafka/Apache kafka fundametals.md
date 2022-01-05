Apache Kafka Fundamentals
--------------
Every company is powered by data. We collect data in, gain insight by analyzing it, manipulate it, and create more as output. It is important to get the data from where it is 
created to where it can be analyzed. For example our clicks on items of interest in websites like Amazon, are turned into recommendations that are shown to us a little later.
The faster we can do this, the more agile and responsive our organizations can be. The less effort we spend on moving data around, the more we can focus on the core business 
at hand.

Before defining apache kafka we are going to define the concept of publish/subscribe messaging and the streaming process. 

The concept of publish/subscribe messaging is a pattern that is characterized by the sender (publisher) of a piece of data (message) not specifically directing it to a receiver. 
Instead, the publisher classifies the message somehow, and that receiver (subscriber) subscribes to receive certain classes of messages. Pub/sub systems often have a broker, a 
central point where messages are published, to facilitate this.

A streaming process is the processing of data in parallelly connected systems. This process allows that one record executes without waiting for the output of the previous record.
Therefore, a distributed streaming platform enables the user to simplify the task of the streaming process and parallel execution. Therefore, a streaming platform in Kafka 
works similar to an enterprise messaging system where it publishes and subscribes streams of records and as soon as the streams of records occur, it processes it.



