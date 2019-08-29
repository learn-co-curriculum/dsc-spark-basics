
# Spark Basics
Authors: Daniel Hinojosa

## Spark Architecture

![Spark Architecture](../images/spark_architecture.png)

## Reason for Spark’s Existence
* CPU went from single to multi-core
* Hard Drive storage became cheap over time
* This allows for processing of data without expense

## Spark Architecture
* The reason for existence is that one computer is too slow for processing data
* A cluster can provide faster processing in parallel.
* Spark is separated by:
  * A _driver_ process
  * An _executor_ process

## The Driver
* The driver system for your application
* Maintains information about the application
* Responds to external programs
* Analyzes work across executors
* Distributes work across executors
* Schedules work across executors

## The Executor

* Executes code assigned to it by the driver
* Reports the state of the computation back to the driver

## Spark Extras

* **_MLlib_** - Machine Learning with Spark
* **_GraphX_** - for Graph Processing
* **_SparkR_** - for working with Clusters using R

## Cluster Manager

* Since Spark is a system where it separates work and distributes them it requires multiple machines
* Thus, it requires a cluster manager to manage the remote nodes, known as cluster mode
* Controls the Physical Machines
* Allocates resources to Spark applications
* Cluster Managers can either be:
  * Sparks in-house cluster manager
  * YARN
  * Mesos

## Local Mode

* Instead of remote machines this will run on your internal box
* Easy for testing, in house demonstrations

## Languages Supported

* Scala (Spark’s default language)
* Python (Does nearly everything that Scala does)
* Java (Louder than Scala)
* SQL (Spark SQL is compliant SQL to interact with querying data)
* R/Spark (The classic Big Data language)

For this class/workshop we will be using Scala since it is 
  less verbose and has other features that Java does not have. It is also
  Spark's default language

## Spark Intro
* Big data processing framework
* Variety of packages built upon Spark engine
* Contains two APIs
  * _Unstructured API_
    * Lower Level
    * `RDD`
    * Accumulators
    * Broadcast Variables
  * _Structured API_
    * Higher Level
    * Optimized
    * `DataFrame`
    * `Dataset`
    * `Spark SQL`

## `RDD`
* `RDD` stands for _Resilient Distributed Dataset_ it is the underlying data structure in which Spark operates
* `RDD` can still be used but they are unoptimized unlike `DataFrame`, `DataSet`, and `SparkSQL`

## You want to use `DataFrame`, `DataSet`, `SparkSQL` over `RDD`

Source: High Performance Spark
by Holden Karau; Rachel Warren
Published by O'Reilly Media, Inc., 2017

Here is a chart which shows the difference in performance with the various data structures in Spark, especially when it comes to aggregations

![execution_time.png](../images/execution_time.png)
