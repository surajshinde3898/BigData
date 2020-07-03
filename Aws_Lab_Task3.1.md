# LAB 3.1 -> Importing RDBMS Data into HDFS

***Objective -> Import data from a database into HDFS.***

***Pre-requisites -> Hadoop cluster on EMR should be up and running***

Following are the steps to be performed in this lab:-

1. Create an Amazon RDS database.

2. Connect this database with MySQL Workbench.

3. Now create a new salaries table using following sql command

    ```
    *create table salaries (
    gender varchar(1),
    age int,
    salary double,
    zipcode int);*
    
    ```
    
 4. Load the data given in salaries.txt file into this salaries table using following sql command

    *load data infile '<path-to-file>/salaries.txt' into table salaries fields terminated by ',' ;*
    
    
    *[Note] ->* If you get an infile error while inserting the data follow below steps:-

        *  Close current SQL connection
        *  Right click on your Connection and select 'Edit Connection'
        *  Click on Advanced
        *  Add following line to 'Others'

            OPT_LOCAL_INFILE=1

        *  Now Reconnect to your database
        
        
 5. Now, ssh to your EMR cluster and make sure Sqoop is pre installed in this cluster.
  
 6. Run sqoop import command to import data from sql database to hdfs
  
  <img src = "https://user-images.githubusercontent.com/63602997/86480732-31551a80-bd6c-11ea-896c-1d5a35b1bd1f.jpg">
  
 7. Now check whether salaries directory is created on hdfs with 5 files present as shown below
  
  <img src = "https://user-images.githubusercontent.com/63602997/86480734-33b77480-bd6c-11ea-8c67-6998d7e8b560.jpg">
  
8. To verify whether data is present in these file use cat comm

  <img src = "https://user-images.githubusercontent.com/63602997/86480741-387c2880-bd6c-11ea-9e01-4f520b603cfb.jpg">
  
9. Now we will import only salary and age data from the database and put it into new directory named salaries2

  <img src = "https://user-images.githubusercontent.com/63602997/86480736-3619ce80-bd6c-11ea-99b9-012594744df4.jpg">
  
10. Now check whether salaries2 directory is created on hdfs with 2 files present as shown below

11. To verify whether data is present in this file use cat command  

   <img src ="https://user-images.githubusercontent.com/63602997/86480741-387c2880-bd6c-11ea-9e01-4f520b603cfb.jpg">
   
12. Now we will use --split-by command to split our data accoring to a certain column value and put it into new directory named salaries3

   <img src = "https://user-images.githubusercontent.com/63602997/86480747-3ade8280-bd6c-11ea-8d27-169c331485f7.jpg">
   
13. Now check whether salaries3 directory is created on hdfs with 3 files present as shown below

   <img src = "https://user-images.githubusercontent.com/63602997/86480765-416cfa00-bd6c-11ea-99b5-ff715c8fd1fc.jpg">
   

  
  
  
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
