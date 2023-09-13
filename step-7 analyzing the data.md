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

# Lets use pyspark.pandas to read file instead pyspark.sql


![Screenshot 47](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/d77f7d16-3549-4407-bf00-286f18169d82)


![Screenshot 48](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/750143fd-a394-4f59-a417-95a0ebd6ed87)


![Screenshot 49](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/52f37525-b616-45c8-b340-30096f72afe5)



![Screenshot 50](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/7966f551-3590-40b2-a532-b3a8900f66e7)


![Screenshot 51](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/21497991-b240-40a9-a183-bf9419ff00fb)



![Screenshot 52](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/79b9e61b-6a26-4778-8ffa-aa089dd8c01b)



![Screenshot 53](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/7d896d60-2774-41c3-9c77-73728900760a)


![Screenshot 54](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/2cc30d77-6ae4-4572-8a69-fa63715591f3)


![Screenshot 55](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/bcccaf30-d85b-4ed9-84ea-3a004486456b)


![Screenshot 56](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/1d698c40-232e-4022-ba6c-783957489c14)


![Screenshot 57](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/062d9244-8e2e-4a55-988e-444bbcac8cd4)




