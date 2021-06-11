In Big Data there are two types of data that we process - batch and streaming data. These terms, batch and streaming, 
refer to the way that we’re getting our data and the speed at which we’re getting our data. 


### 1 - Batch Data 

Batch data is data that we have in storage and that we process all at once, or in a batch. Say for example that someone gives you a large jar of candies and asks you
to count all of the candies in the jar. That is a simple example of a batch job - we take candies that were already present in some form of storage (in this case, a jar) 
and count them. Since we count all of the candies one time, this is considered batch processing. 


A real-world example of batch processing is how telecommunication companies process cellular phone usage each month to generate our monthly phone bills. 
To do this they process batch data - the phone calls you’ve made, text messages you've sent, and any additional charges you’ve incurred through that billing cycle, 
to generate your bill. They process that batch data in a batch job. 

![](Img/Batch.PNG)

### 2 - Streaming Data

Streaming data is data that is being continually produced by one or more sources and therefore must be processed incrementally as it arrives. 
Now, what if instead of counting candy sitting in a jar, we are asked to count candy coming towards us on a conveyor belt? As the candy reaches us, we have to count 
the new pieces and constantly update our overall candy count. In a streaming job, our final count is changing in real-time as more and more candy arrives on the conveyor 
elt.


A real-world example of stream processing is how heart monitors work. All-day long, as you wear your heart monitor, it receives new data - dozens of thousands of 
data points per day as your heart beats. Every time your heart beats new data is added to your heart monitor in real-time. If your heart monitor has a display of your
average heartbeat for the day, that average must be constantly updated with the new numbers from the incoming stream of data.


![](Img/Streaming.png)
