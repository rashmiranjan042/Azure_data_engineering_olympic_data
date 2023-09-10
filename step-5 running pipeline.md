# careating copy activity pipeline

here we extract the data from github repository to azure storage account .

click on create a new pipeline

![Screenshot 16](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/db854f0d-6db8-4dfc-aea3-f17200f46167)

darg and drop copy activity

click on copy activity 

it show us options fill the details required.

we have to provide source and sink location to perform this data movement activity.

for creating source we have to create a dataset , in that data set we have to provide linked service which will connect to git hub repo .
there we provide integration runtime through which all the computation work going to be done.

click on source , click on +new 

![Screenshot 17](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/4f45727d-ec3e-4906-9a61-4a86e86a5e4b)

Here our data resides in web so we give the http .
format of file csv , which is our data type format.

![Screenshot 18](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/21cc047e-c5eb-4df8-9d7e-c6640d3a759c)

click continue.

Here we have to provide the data set name and create a linked service , which will establish a connection bewtween adf and github.

![Screenshot 19](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/e7a9db26-df27-43ae-9310-25cb91a22aa0)

lets create a linked service

provide the name as you want.

choose integration runtime.

 here we choose azure auto resolve integration runtime.

 ![Screenshot 20](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/5a2c3400-fa2c-469c-bd86-6ec7a0c7c8b6)

Provide the base url where data resides.

click on github dataset, click on raw , copy the hhtps://... and paste i base url.

 ![Screenshot 21](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/f8f2414a-0e3c-49b8-9029-ba7dbb315f17)

Then we have to sink this data to our azure storage account container, where our folders reside , here which is azure data lake gen2 as we create.

click on sink 

click on new

select azure data lake gen2 

select the file format we want to store the data.

Here csv.

provide the location we want to store the file.

select first row has header.
 
 schema none

Because the file we have haven't schema architecture.




