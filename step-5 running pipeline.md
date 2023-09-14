# careating copy activity pipeline

here we extract the data from github repository to azure storage account .

- click on create a new pipeline

![Screenshot 16](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/db854f0d-6db8-4dfc-aea3-f17200f46167)

- darg and drop copy activity

- click on copy activity 

it show us options fill the details required.

- we have to provide **source and sink location** to perform this data movement activity.

 for creating source we have to create a dataset , in that data set we have to provide linked service which will connect to git hub 
 repo .

- There we provide **integration runtime through which all the computation work going to be done.**

**click on source** 
---
- click on +new 

![Screenshot 17](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/4f45727d-ec3e-4906-9a61-4a86e86a5e4b)

Here our data resides in web.

- so we give the http .

- format of file csv , which is our data type format.

![Screenshot 18](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/21cc047e-c5eb-4df8-9d7e-c6640d3a759c)

click continue.

- Here we have to provide the data set name and create a linked service , which will establish a connection bewtween adf and github.

![Screenshot 19](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/e7a9db26-df27-43ae-9310-25cb91a22aa0)

- lets create a linked service

- provide the name as you want.

- choose integration runtime.

 here we choose azure auto resolve integration runtime.

 ![Screenshot 20](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/5a2c3400-fa2c-469c-bd86-6ec7a0c7c8b6)

- Provide the base url where data resides.

- click on github dataset, click on raw , copy the hhtps://... and paste in base url.

 ![Screenshot 21](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/f8f2414a-0e3c-49b8-9029-ba7dbb315f17)



![Screenshot 22](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/45c26ef3-f549-4588-9be2-3c814e6b3ee0)

- then click create,

which will create our linked service for data set.

- select the linked service we create

![Screenshot 23](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/d38570e6-5244-4619-ae75-9f47742f36cf)

- select **first row as header.**

- here the data set we have dont follow a schema so we choose none.

- click ok.
---
**sink**
---

Then we have to sink this data to our azure storage account container, where our folders reside , here which is azure data lake gen2 as we create.

- click on sink 

![Screenshot 24](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/a559f10b-8099-4be7-9304-dec5c57162f0)

- click on new

- select **azure data lake gen2** 

- select the **file format we want to store the data.**

- Here we choose csv.

**note**
 by **choosing different fomat we can format the file type into other like avro, parquet, binary etc.**

- provide the location we want to store the file.

- create a linked service where our sink dataset reference to the azure data lake storage gen2 folder.

---

**note**

here when we are going to sink with azure stoage account.

Here it asks some extra configure things to create a linked service.

- Authentiacation type.

- Account selection method

- click on from azure subscription

- choose subscription type

- give stoarage account name

where our container and folders reside to store the data for us.

![Screenshot 25](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/f1fb5519-a699-4dba-bb08-98551e02b692)


AFter providing all the details click on create.

it will create a suucessful linked service.

![Screenshot 26](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/ca48cb6b-d23d-40ad-9851-6c1ddada4090)

- click on folder icon to set location where we want to store the file.

go with the hierarchy.

As we do in our windows sysyem when we have to choose a file location.

then give it a name to file which will going to store the data.

-select first row has header.

![Screenshot 27](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/ec66d152-7f11-46ff-9a0e-7f79600a6c7a)

-  schema none

Because the file we have haven't schema architecture.

click ok to complete one activity.

using this same method we create 5 data copy activity ,
to store these 5 files.

**note**

we will create linked service for each source file,
but we don't need to create multiple linked service for sink.

**using the same linked service of sink we can store 5 source datasets into data lake gen2 .**

- Then we connect all the 5 activities in the pipeline1 , that we create.

**we drag the blue ➡ arrow to link with next one**, this blue arrow represents after successful run of this activity, the next activity will run.

![Screenshot 28](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/c50dc8ee-cbbf-4794-bf2e-1193b1c3b692)

Then we validate all .

- click the publish all , where all our pipeline, integration runtime, linked service everything will save and activate.

- To run the pipeline click on trigeer. 

Here we have options trigger now and new /edit trigger where we can set the type of trigger we want.

we run tigger now. 

![Screenshot 29](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/f78fdc78-3bd4-461a-9c01-35895e2b9fb7)

In monitor section we will monitor 

1) pipeline run

2) trigger run

3) integration runntime

After the pipeline run succeded

we will go to our storage account and look at the data stored in our raw data folder.

![Screenshot 30](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/33a01ab2-0349-4987-9cd0-f60b0f5f37ad)

