# Analyzing olympic data.

As i am using databricks community edition 

lets see how to upload data to dbfs and access it.

then perform analyze on top of that data.

![Screenshot 42](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/d4fe50d0-ae1b-4ccb-877b-6c68f8f34015)

# Accessing data from DBFS

After uploading the data to dbfs.

click on data 

go to dbfs

click on the file , copy path

copy spark api format.

![Screenshot 45](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/2b8b85ce-248d-4760-af0c-d2353d68f186)


write the code to read the file from dbfs.

![Screenshot 46](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/127e6fcf-28f4-4b06-a58c-e08d8e6992df)

athlets=spark.read.csv("dbfs:/FileStore/Athletes.csv",header=True,inferSchema=True)

athlets.show()


coaches=spark.read.csv("dbfs:/FileStore/Coaches.csv",inferSchema=True,header=True)

coaches.show()


entriesGender=spark.read.csv("dbfs:/FileStore/EntriesGender.csv",inferSchema=True,header=True)

entriesGender.show()


medals=spark.read.csv("dbfs:/FileStore/Medals.csv",inferSchema=True,header=True)

medals.show()

teams=spark.read.csv("dbfs:/FileStore/Teams.csv",inferSchema=True,header=True)

teams.show()

By doing this **we convert the files into data frame** and assign into the variable.

# Things we are going to look at 


1) top 5 countries Rank On  gold medals.

2) No of paticipants from each country

3) 



