# Lets perform etl using ADF

-It is the cloud based etl and data integration service.

- That allows us to **create data driven workflows** for orchestrating data movement and transformation at scale.

**it is not the oltp**

- Here we only **orchestrate data movement and do some transformation.**

- click in the resource group.

- click on adf name you provide to create here i provide dataparactice .

![Screenshot 8](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/4b102396-889e-4427-ba42-e34390b95947)


- click on **launch studio to launch data factory.**

- it will open in a new tab. it looks like something this.

There are 4 main sections available.

- **Home**

- **Author**

- **Monitor**

- **Manage**

## Home 

- IN home , it gives us direct operation links to help us.

## Ingest

![Screenshot 9](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/3e82aa9c-f658-46ba-ad5c-ed0750d8901f)

- it will ask us to fill the details about data and the source location also about triggers to set and the location to store the copy data.

- But mostly we dont do ingest data using this method , we go to author mode which is the most appropriate method to do all the operation.

- To step back from this tab click on cancel button which is placed righmost bottom of the page.

## Orchestrate

- when we click on this 

![Screenshot10](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/816ec8c9-017b-4147-a8bf-bedc5a86955b)

- it will open author page and create a pipeline1 and ask  us to do etl activities

- and run the pipeline.

- To close this tab click ❎ on pipeline1 and discard changes to back home.

## Transform Data

![Screenshot 11](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/2f853c31-aa70-4890-a746-f872be32dddc)

- After the data resides in datasets .

-  lets perform **data operations or transforms** through **sql quries** using data flows .

- Data flows also called mapping data flows.

-  Because here we dont write query hands on we just drag and drop all the oparations

-   by click ➕ on source button.

- when we click on tranform it will take us to author page and there  it will create data flow .

- where we provide the source , on the top of that we will do some transformation using ➕ , it will ask us sql query operation in the form of drag and drop ,like join,union,aggregation,filter etc.

- Then provide the sink location to store the transformed data.

- To get back from this page click on the dataflow1 name and cancel and click on discard and close.

## configure ssis

![Screenshot 12](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/3bd514c5-5855-4c14-8523-ebab27cf8a97)


- **Integration runtime is the compute infrastructure** use by Adf to provide integrartion capabilities over different network environment.

There are 3 types of integreation runtimes.

1) azure integration runtime
   
2) self hosted integration runtime

3) azure ssis( sql service integration service) integration runtime

## when to use what kind of ir ?

1) for azure services, like if you want to perform copy activities between azure services like, azure blob storage, sql server, cosmos db and other azure owned databae service, we will run azure integration runtime.

2) for on-premises, virtual network , use azure self hosted integration runtime

3) for your ssis packages use ssis integration runtime.

when we click on the configure ssis, it will open a window for integration runtime setup.

which ssis type.

using this you will pick up your ssis to cloud.

## note 
- if you have to **use data flows, in your data pipeline, you shouldn't use self hosted, because it is not supported.**

- Here you have first stage/store the data on cloud, then use azure integration runtime to run dataflows on the top of that data set.

- to get back from this configure ssis page to home click on cancel button on the right bottom .

- again click on cancel

- it will take back to you manage integration runtime page.

- Where you can create integration runtime.



# author

![Screenshot 13](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/f3db49c0-3075-4849-a50e-6a12a4f69f54)

when we click on author, as we can see that there 5 things availbe to do operation.

1)pipeline

2)change data capture (cdc preview)

3)datasets

4)data flows

5)power query

using this we will create a pipeline and run activities .

cdc in preview phase it will lauch by azure in upcoming days in which it will going to be stable.

## pipeline

In pipeline there are lot of activities to do on data.

lets create a pipeline 

![Screenshot 14](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/f62a1ea3-b4e1-4f51-80cf-d6b94fe8e887)

click on ..., right side of pipeline to create a pipeline named as pipeline1.

**we also create a folder of pipeline to run.**

![Screenshot 15](https://github.com/rashmiranjan042/Azure_data_engineering_olympic_data/assets/106671482/514ed348-21e2-4f5b-a9b5-e928fd7f21ef)


Here we can rename the pipeline.

These are the activities perform in a pipeline to build a successful pipeline to run.

## activities  

**Activities represent a processing step in a pipeline.**

There are 3 types of activities.

a) Data movemnt activities

b) Data transformation activities

c) control flow activities

## datsets

Datasets are the reference point of the data we ant to use in our activities  as inputs or outputs.

In this project , the datasets are the reference point to raw data directory which reside in container. 

where we are going to ingest the data and store in raw data.

## linked service

Linked services are like connect strings, which define the connection information that's needed for data factory to connect to external sources.

## data flow

Using data flow we create visually designed transformaqtions in azure data factory.

Data flows allow data engineers to develop data transformation logic without writting code.

This data flow run on adf managed clusters for scaled out data processing.



## validation and publish all

click on validate to check the validation of code or activies.

publich all is the save option.


## trigger

after publishing the pipeline ,

we need to run the pipeline

to run a pipeline we set triger .

Triggers represent a unit of processing that determines when a pipeline exzecution need to be kicked off.

## types
1) scheduled trigger   ( A trigger that invokes a pipeline on a wall clock schedule )

2) tumbling window trigger  ( a trigger that operates on a periodic interval)

3) event based trigger    ( A trigger that responds to an event)

