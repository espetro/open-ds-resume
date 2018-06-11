## Part III: SparkContext - Application Programming



### SparkContext `sc`

It is automatically initialized when the Spark Shell is started; however, **it must be imported when running a Spark Application**. 

#### Declaration and imports

- To write a Scala application, you need to add a Maven dependency on Spark.

  ```scala
  import org.apache.spark.SparkContext
  import org.apache.spark.SparkContext._
  import org.apache.spark.SparkConf
  ```

- To write a Python application, `from pyspark import SparkContext as sc, SparkConf as scf`.

- To connect to a *HDFS* cluster, yo need to add a dependency on `hadoop-client`.

#### Initialization

1. Scala:

2. Python:

   `conf = scf().setAppName(appName).setMaster(master)`

   Where

   - appName is the String name
   - master is a Mesos/YARN cluster URL (launch spark-submit).

3. Hadoop:

### Spark API: passing functions to Spark

- Anonymous functions

  `rdd.map(lambda x: line.split())`

- Static methods in a global, singleton object

  ```python
  class myFunctions:
      def __init__:
          return
      def func1():
          return
      def func2():
          return
      
  # [...]
  functions = new myFunctions()
  rdd.map(functions.func1)
  ```

- Passing by reference



#### Programming the business logic

1. Get Spark's API
2. Create the RDD from an external DB or an existing RDD
3. Combine Transformations and Actions
4. Use RDD persistence to improve performance
5. Use broadcast variables or accumulators for specific variables

You can see how this works by **running Spark examples** on `./bin/spark-submit examples/src/main/python/pi.py`.

#### Standalone applications

```python
"""SimpleApp.py"""
from pyspark import SparkContext

logFile = "$SPARK_HOME/log.txt"
sc = SparkContext("local", "Simple App")
logData = sc.textFile(logFile).cache()

numAs = logData.filter(lambda l: 'a' in l).count()

print("Lines with a:{}".format(numAs))
```

- Define the dependencies: with `--py-files`
- Setup a .py or .zip as packaged application

#### Submit applications to Spark Cluster

```bash
./bin/spark-submit \
--class <main-class> \
--master <master-url> \
--deploy-mode <deploy-mode> \
--conf <key>=<value> \
<application-jar> \
[app-args]
# -------
./bin/spark-submit \
--class org.apache.spark.examples.SparkPi \
--master local[4] \ # run locally on 4 cores
/path/to/examples.jar \
100
```



