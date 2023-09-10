# Adding services to the resource group
click on the resource groups to see the resource group that we create.

click on that name we give for our resource group name.

lets add the azure services to the group for our project

In this project we are going to use
Azure blob storage , which resides in azure storage account.

using azure blob storage we will create azure data lake gen2

Then we create container inside container we add directories or folders.

inside that folder we ingest the data using  azure datafactory for etl .
after that we will use azure data bricks to analyze the data and make reports.

# creating azure data lake gen 2 using blob storage.

lets understand this little bit.

azure data lake gen2 is the combination of hadoop and azure blob storage.

where we can store 3 types of data structure.

# structured data
# semi structured data
# unstructured data.

# Note 
By a single check box we can covert our simple blob storage to azure data lake gen2.

# lets do that.

search azure storage account.

provide the details.

![Screenshot 2](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/2b3d5b2c-908f-4d19-b737-c0b9e4befb82)

important to select the type of redundancy .
There are 3 types of redundancy available to provide the high availablity feature of cloud.

lrs(locally redundant storage),

zrs(zone redundant storage),

grs(geo redundant storage).

To prevent from any failure.

![Screenshot 3](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/58fc8dc4-a29d-4539-ab52-94994470e7fd)

click on next to go advance section.
There we have to click the checkbox ☑ of hierarchical namespace.

![Screenshot 4](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/575072eb-40c2-45af-af3f-c51b2bb867e3)

This convert to azure data lake gen2.

![Screenshot 4 5](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/58b2bf95-c884-4097-8f18-8901db40bfcc)

Here we select the tire of  Access
cool, hot , archieve.

Hot is used for storing data that is accessed frequently.

cool is used for storing the data that is infrequently accessed and stored for at least 30 days.

Archieve is used for storing data that is rarely accessed and stored for at leat 180 days .

click create to create.

# lets add azure data factory to our resource group

In home search data factory.
click on data factory then create one.

![Screenshot 5](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/a896860a-2aae-4e22-b349-bea3fd314e93)

provide the reource group name then click on review and create.


After performing etl we will look at how to analyze the data using azure data bricks.
