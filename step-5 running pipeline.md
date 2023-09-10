# careating copy activity pipeline

here we extract the data from github repository to azure storage account .

click on create a new pipeline

screenshot 16

darg and drop copy activity

click on copy activity 

it show us options fill the details required.

we have to provide source and sink location to perform this data movement activity.

for creating source we have to create a dataset , in that data set we have to provide linked service which will connect to git hub repo .
there we provide integration runtime through which all the computation work going to be done.

click on source , click on +new 

screenshot 17

Here our data resides in web so we give the http .
format of file csv , which is our data type format.

screenshot 18

click continue.

Here we have to provide the data set name and create a linked service , which will establish a connection bewtween adf and github.


Then we have to sink this data to our azure storage account container, where our folders reside , here which is azure data lake gen2 as we create

click on sink 

click on new

select azure data lake gen2 

select the file format we want to store the data.

Here csv.

provide the location we want to store the file.

select first row has header.
 
 schema none

Because the file we have haven't schema architecture.




