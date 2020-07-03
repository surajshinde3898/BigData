# LAB 3.2 -> Exporting HDFS Data to an RDBMS

***Objective -> Export data from HDFS into a MySQL table using Sqoop.***

***Pre-requisites -> Hadoop cluster on EMR should be up and running***

Following are the steps to be performed in this lab:-

1. Create a new hdfs directory using mkdir command with name salarydata
# hdfs dfs mkdir salartdata

2. Put salarydata.txt into the salarydata directory in HDFS

<img src = "https://user-images.githubusercontent.com/63602997/86484650-5483c800-bd74-11ea-986f-0e01f58198a9.jpg">

3. Check whether the file is created on hdfs


4. Create a new Table in the Database as salaries2 using following sql command

*create table salaries2 (
gender varchar(1),
age int,
salary double,
zipcode int);*

5. Now export data from hdfs to database

<img src = "https://user-images.githubusercontent.com/63602997/86480752-3d40dc80-bd6c-11ea-9d54-0e90376a5b15.jpg">

6. Verify whether all records are been exported successfully

<img src = "https://user-images.githubusercontent.com/63602997/86480770-4467ea80-bd6c-11ea-9e46-71f4a61a8aac.jpg">
