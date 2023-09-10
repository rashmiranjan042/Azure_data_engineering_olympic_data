# azure data lake gen2
click on the account name we give for our stroge account to store data in azure data lake.

In the data and storage section , there are 4 options available to store different type of data.

container

file share

queue

tables

lets create container to store the data.
inside container we also add directory , so that our data store in different folders.

IN container there is a bydefault container availabe which store our log data.

click on + container to create one container and give container name ,
create

click on the container name, to go inside container. lets create folder by 

click on add directory.

provide the name and save. lets name it as raw data.

IN this folder we are going to add the data , through adf which going to pick data from our source, Here this is github.

in organisation source may be anything, it may be our blob storage, data lake, or other storage services like sql server, cosmos db,or multicould system like , your data may be reside in aws s3 or google bigquery.

using Adf(azure data factory)  we can ingest the data into our folders created in containers of azure storage account .

Here we created azure data lake gen2 created completely with a container containing 2 folders Raw data And Transformdata.
