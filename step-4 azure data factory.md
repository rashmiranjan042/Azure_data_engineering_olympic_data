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

