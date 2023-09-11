# Data Bricks

lets understand this little bit, then we perform our Analytics.

Before going to databricks lets know a little bit about spark

# Apache Spark

spark is an open source unified analytics engine for large scale of data processing.

These are the features.

1) FAST and Efficient
2) In memory engine
3) Highly Scalable Architecture
4) Unifies Vareity of use cases

# Hadoop

Hadoop is an open-source distributed storage and processing framework. 

It is primarily used for storing and processing **large volumes of data across a cluster of commodity hardware**.

understand this line in hirarchy level, at last the data going to be stored at hardware.

It uses **HDFS** hadoop distributed file system.

A filesystem is a method of storing / finding files on a hard disk.

It uses **MAPREDUCE** programming model to process the data.

which is written on **Java**.

# DATABRICKS

Databricks is a cloud-based analytics platform that is built on top of Apache Spark, which is a fast and general-purpose cluster computing system. 

**cluster** Have the spark engine and other compnents that make the computation successful.

 Databricks integrates with a wide range of data sources and services,
 
 including data lakes, databases, and third-party libraries.

 so by integrating with data lake we run our project.

 # lets create cluster and mount the data lake to databricks.

 Here I am using the data bricks community edition.

 But most of the things are similar to enterprise editon.

 IN community edition we can connect with cloud service like azure , aws, gcp.

 **creating cluster**
 
click on compute,

provide cluster name

choose cluster mode

select data bricks runtime version
 
☑ Enable auto scaling

☑ Terminate after 120 minutes of inactivity.

worker type

choose the memory size and dbu you require to compute.  

Here we took 14 gb mem ,4 core, 0.75 dbu which is lower.       

choose min workers max workers

Here this workers min to max workers are autoscale.

driver type 

same as worker

In community edition we have to just provide compute name.

click create to create.

![Screenshot 31](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/d92d1e47-1f11-4597-8dc5-65454915abc5)

after 4 to 5 min it will create cluster for you.
