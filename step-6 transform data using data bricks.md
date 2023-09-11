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

![Screenshot 32](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/ec3e3ae0-ecd7-42ef-a20d-bd30c31c1ca7)
Cluster Dashboard:

This is the cluster dashboard  where we

Select the cluster we want to monitor.

The Cluster Dashboard provides an overview of cluster resource usage, including CPU, memory, and network metrics. You can view historical data and real-time metrics here.

Metrics:

Within the Cluster Dashboard, you can access specific metrics for driver and worker nodes. This allows you to monitor memory and CPU usage on a per-node basis.

 so that we can track the resource and accumulate the usage of resouce.

Click on create 

create notebook 

![Screenshot 33](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/88b49430-84b2-4d35-a46b-0df2d5e79adb)

where we are going to mount our adls gen2 and perform operation on the data.

# mount azure adls gen2 container to databricks

**note**

IN databricks we dont need to create a spark session as we do in google collab.

just type

spark

in notebook , it will show all the details.

![Screenshot 37](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/51a0e431-b2fe-48ff-8d1c-df8cc51245ff)

**mount code**

![Screenshot 38](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/83d6648a-a3af-4299-ab24-205686f720b3)

source="wasbs://<container-name>@<storageaccount-name>.blob.core.windows.net"

mount_point="/mnt/<mount-name>"

conf_key="fs.azure.accountkey.<storage-account-name>.blob.core.windows.net"

key_name="<access_key>"

**or sas key(shared access signature)**

conf_key="fs.azure.sas.<container-name>.<storage-account-name>blob.core.windows.net"

key_name="<sas_key>"


 **<> in this location we are going to provide value**
 
 **then delete this operator.**
 
 **here the mount name give it will create that folder.**

dbutils.fs.mount( 

source = source,

mount_point= mount_point,

extra-configs={conf_key:key_name}

)

![Screenshot 39](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/8490d455-9037-4ae1-875e-eba2cef00cd2)

**%fs**
**ls /mnt/<mount_name>** 

 the name we give at the time of mounting

 it will show us the folders inside our **olympicdata2021 container**

 **raw data**

 **transformed data**
 
![Screenshot 40 (2)](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/e2190757-f145-4899-b139-0f4824758f7b)


![Screenshot 41](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/0f1abb9c-6f4f-4d13-9ce4-27b77af81b53)



