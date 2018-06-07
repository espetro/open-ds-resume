

- Data is increasing in volume velocity variety
- Apache spark is *fast* and *general-purpose*.
  - Faster than *Hadoop's MapReduce* for complex in-memory applications
  - Bath applications
  - APIs for Scala, Python, Java, R. Libraries for SQL, Machine Learning, Streaming.
  - Interactive queries and streaming
  - Runs on Hadoop clusters or as a standalone.
  - Fault tolerance on commodity hardware
  - Parallel distributed processing



- For Data Scientists
  - Analyze and model the data, to obtain insight using ad-hoc analysis
  - transforming the data into a useable format
  - Statistic, machine learning, SQL



![](/home/flamenquim/Dropbox/BigData/Distributed-Processing/assets/spark-stack.png)



- Spark SQL
  - Works with SQL and HiveQL
- Spark Streaming
  - Provides processing of live streams of data or stored in memory.
- ML lib
  - Provides multiples types of machine learning algorithms
- GraphX
  - Provides proccessing on graph parallel manipulations 



### [RDD] Resilient Distributed Datasets

![](/home/flamenquim/Dropbox/BigData/Distributed-Processing/assets/reduced-rdd.png)

- Operations
  - Transformations: void methods, lazy evaluations, creates a DAG
  - Actions: function methods, performs the transformations and the action that follows



### Programming aspects of Spark

- Everything is an Object (Spark is based on Scala)

  - Numbers are Objects (Integer, Double, ...)
  - Functions are objects
    - `def fnName ([list params]): [return type]`
    - pass functions as arguments

- Anonymous functions

  ```scala
  def main() {
      oncePerSecond(() => {
          println("time flies")
      })
  }
  ```



##### Using Spark with Scala

- launch: `./bin/spark-shell`
- read in: `val textFile = sc.textFile("README.md")`

##### Using Spark with Python

- launch: `pyspark`
- read in: `textFile = sc.textFile("README.md")`

