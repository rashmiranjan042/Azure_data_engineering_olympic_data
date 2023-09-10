# Lets perform etl using ADF

click in the resource group.

click on adf name you provide to create here i provide dataparactice .

click on launch studio to launch data factory.

it will open in a new tab. it looks like spmething this.

There are 4 main sections available.

Home

Author

Monitor

Manage

# Home 
IN home , it gives us direct operation links to help us.

# Ingest

it will ask us to fill the details about data and the source location also about triggers to set and the location to store the copy data.

But mostly we dont do ingest data using this method , we go to author mode which is the most appropriate method to do all the operation.

To step back from this tab click on cancel button which is placed righmost bottom of the page.

# Orchestrate

when we click on this 

it will open author page and create a pipeline1 and ask  us to do etl activities

and run the pipeline.

To close this tab click ❎ on pipeline1 and discard changes to back home.

# Transform Data

After the data resides in datasets , lets perform data operations or transforms through sql quries using data flows .

Data flows also called mapping data flows because here we dont write query hands on we just drag and drop all the oparations by click ➕ on source button.

when we click on tranform it will take us to author page and there  it will create data flow .
 where we provide the source , on the top of that we will do some transformation using ➕ , it will ask us sql query operation in the form of drag and drop ,like join,union,aggregation,filter etc.

Then provide the sink location to store the transformed data.

To get back from this page click on the dataflow1 name and cancel and click on discard and close.

# configure ssis

Integration runtime is the compute infrastructure us by Adf to provide integrartion capabilities over different network environment.

There are 3 types of integreation runtimes.

1) azure integration runtime
2) self hosted integration runtime
3)azure ssis( sql service integration service) integration runtime

# when to use what kind of ir ?

1) for azure services, like if you want to perform copy activities between azure services like, azure blob storage, sql server, cosmos db and other azure owned databae service, we will run azure integration runtime.
2) for onpremises, virtual network , use azure self hosted integration runtime
3) for your ssis packages use ssis integration runtime.

when we click on the configure ssis, it will open a window for integration runtime setup.

which ssis type.

using this you will pick up your ssis to cloud.

# note 
if you have to use data flows, in your data pipeline, you shouldn't use self hosted, because it is not supported.

Here you have first stage/store the data on cloud, then use azure integration runtime to run dataflows on the top of that data set.

to get back from this configure ssis page to home click on cancel button on the right bottom .

again click on cancel

it will take back to you manage integration runtime page.

Where you can create integration runtime.
