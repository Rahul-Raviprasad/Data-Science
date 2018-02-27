# Spark Streaming

As an extension to Apache Spark API, Spark Streaming is fault tolerant, high throughput system. It processes the live stream of data.

Spark Streaming processes the live stream of data. It takes input from various reliable inputs sources like Flume, HDFS, and Kafka etc. and then sends the processed data to filesystems, database or live dashboards. The input data stream is divided into the batches of data and then generates the final stream of the result in batches.


Its key abstraction is Apache Spark Discretized Stream or, in short, a Spark DStreams which represents a stream of data divided into small batches. DStreams are built on Spark RDDs, Spark’s core data abstraction. This allows Streaming in Spark to seamlessly integrate with any other Apache Spark components like Spark MLlib and Spark SQL.

How does Spark Streaming works?

In Spark Streaming data stream is divided into batches called DStreams, which internally is a sequence of RDDs. The RDDs are then processed using Spark APIs, and the results are returned in batches.

Spark Streaming provides an API in Scala, Java, and Python. The Python API was recently introduced in Spark 1.2 and still lacks many features.

Spark Streaming maintains a state based on data coming in a stream and this is called as stateful computations. It also allows window operations (i.e., allows the developer to specify a time frame to perform operations on the data that flows in that time window). There is sliding interval in the window, which is the time interval of updating the window.

Goals of Spark Streaming

Dynamic load balancing
Fast failure and straggler recovery
Unification of batch, streaming and interactive analytics
Advanced analytics like machine learning and interactive SQL
Performance
Hence, DStreams like RDDs are executed lazily by the output operations. Specifically, received data is processed forcefully by RDD actions inside the DStream output operations. By default, output operations are executed one-at-a-time. And they are executed in the order they are defined in the Spark applications.

there is many more to learn about Spark Streaming like:

Why Streaming in Spark?
Spark Streaming Architecture and Advantages
Spark Streaming Sources
Even to know complete Information on Spark Streaming. Go through following link:

Spark Streaming Tutorial for Beginners

learn more through frequently asked questions on Apache Spark. follow link:

Brace your Apache Spark skills with Spark MCQ quiz
