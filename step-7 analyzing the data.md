# Analyzing olympic data.

- As i am using databricks community edition 

- lets see how to upload data to dbfs and access it.

   then perform analyze on top of that data.

![Screenshot 42](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/d4fe50d0-ae1b-4ccb-877b-6c68f8f34015)

## Accessing data from DBFS

After uploading the data to dbfs.

- click on data 

- go to dbfs

- click on the file , copy path

- copy spark api format.

![Screenshot 45](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/2b8b85ce-248d-4760-af0c-d2353d68f186)


write the code to read the file from dbfs.

![Screenshot 46](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/127e6fcf-28f4-4b06-a58c-e08d8e6992df)

```python
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
```

By doing this **we convert the files into data frame** and assign into the variable.

## Lets use pyspark.pandas to read file instead pyspark.sql


![Screenshot 47](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/d77f7d16-3549-4407-bf00-286f18169d82)

```python
spark
```

![Screenshot 48](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/750143fd-a394-4f59-a417-95a0ebd6ed87)

```python
import pyspark.pandas as pd
pd
```

![Screenshot 49](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/52f37525-b616-45c8-b340-30096f72afe5)

```python
athlets=pd.read_csv('dbfs:/FileStore/Athletes.csv')
athlets.head(100)
```

![Screenshot 50](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/7966f551-3590-40b2-a532-b3a8900f66e7)


```python
athlets.info()
```


![Screenshot 51](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/21497991-b240-40a9-a183-bf9419ff00fb)

```python
athlets.shape

athlets.shape[0]

# total participants player = 11085
```


![Screenshot 52](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/79b9e61b-6a26-4778-8ffa-aa089dd8c01b)

```python
# lets group by noc to find total countries and their players.

no_of_countries=athlets.groupby('NOC')
```
![Screenshot 53](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/7d896d60-2774-41c3-9c77-73728900760a)

```python
len(athlets)
```
```python
no_of_countries
```
![Screenshot 54](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/2cc30d77-6ae4-4572-8a69-fa63715591f3)

```python
country_players=no_of_countries.size().sort_values(ascending=False)
country_players
# total no_of_Players of each country
```

![Screenshot 55](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/bcccaf30-d85b-4ed9-84ea-3a004486456b)

```python
toatl_countries=no_of_countries.size().sort_values(ascending=False).count()

# total countries parcticipated in olypmpics

toatl_countries

#206 countries
```

![Screenshot 56](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/1d698c40-232e-4022-ba6c-783957489c14)

```python
# no of disciplined / games played in olympics.

no_of_dicsipline= athlets.groupby('Discipline')
```
```python
no_of_dicsipline.size().sort_values(ascending=False)
```

![Screenshot 57](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/062d9244-8e2e-4a55-988e-444bbcac8cd4)

```python
toatal_discipline=no_of_dicsipline.size().sort_values(ascending=False).count()

toatal_discipline
# no_of_discipline = 46
```

![Screenshot 58](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/53904ff3-c9d0-4446-b09f-0e36550b230e)



![Screenshot 59](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/109c5dd8-536a-40fa-9ef4-e1cae06233ba)


![Screenshot 60](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/cc405faa-ec80-40ed-adf2-b9eab58aff01)



![Screenshot 61](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/af3429cc-ed22-4ee7-9780-13d2f5994495)



![Screenshot 62](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/2fecc5c5-3e72-4344-852f-4de7aeccdfe9)



![Screenshot 63](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/aa5d21fb-aa2c-49b8-923b-089f7a3ce42a)
