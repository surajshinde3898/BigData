# HDFS COMMANDS USING AWS EMR

### Step 1:-
create the aws emr hadoop cluster.

### step 2:-
**Download lab file in AWS EMR.**

### step 3:-
**Unzip the downloaded zip file.**

<img src = "https://user-images.githubusercontent.com/63716706/85947115-77723e80-b966-11ea-87ae-34ff6e2f6e7c.PNG" width = 700>

## 1)View the hdfs dfs Command

<img src = "https://user-images.githubusercontent.com/63716706/85947119-79d49880-b966-11ea-9c28-e632f60f2925.PNG">

## 2) Create a Directory in HDFS
**a.Enter the following -ls command to view the contents of the user’s root directory  in HDFS, which is /user/root.**

You do not have any files in /user/root yet, so no output is displayed.  Run the -ls command again, but this time specify the root HDFS folder:

<img src ="https://user-images.githubusercontent.com/63716706/85947121-7b9e5c00-b966-11ea-82a9-79fc461fcec0.PNG">

Notice how adding the / in the -ls command caused the contents of the root  folder to display, but leaving off the / showed the contents of /user/root, which  is the default prefix if you leave off the leading / on any of the hadoop commands  (assuming the command is run by the “root” user).  

**b.Enter the following command to create a directory named test in HDFS:**

**c.Verify that the folder was created successfully:** 

<img src = "https://user-images.githubusercontent.com/63716706/85947123-7d681f80-b966-11ea-829d-e357071c8f1e.PNG">

**d.Create a couple of subdirectories for test:** 

Notice how the -p command can be used to create multiple directories. The  second command above will fail if you omit the -p.   

**e.Use the -ls command to view the contents of /user/root:** 
Notice you only see the test directory. To recursively view the contents of a folder,  use -ls -R: 

## 3) Delete a Directory  
**a. Delete the test2 folder (and recursively, its subcontents) using the -rm -R  command:**

<img src = "https://user-images.githubusercontent.com/63716706/85947178-bf916100-b966-11ea-8602-679687343611.PNG">

**b. Now run the -ls -R command:**   

## 4) Upload a File to HDFS  
**a. Now let’s put a file into the test folder. Change directories to  /root/devph/labs/Lab2.1:**

**b. Notice this folder contains a file named data.txt:**

**c.Run the following -put command to copy data.txt into the test folder in HDFS:**

**d.Verify that the file is in HDFS by listing the contents of test:**

<img src = "https://user-images.githubusercontent.com/63716706/85947181-c0c28e00-b966-11ea-8415-0a2ce942f5bd.PNG">

<img src = "https://user-images.githubusercontent.com/63716706/85947182-c0c28e00-b966-11ea-95fb-cafff4ea3e21.PNG">

## 5) Copy a File in HDFS  
**a. Now copy the data.txt file in test to another folder in HDFS using the -cp  command:**

**b. Verify that the file is in both places by using the -ls -R command on test. The  output should look like the following:**

**c. Now delete the data2.txt file using the -rm command:**

<img src = "https://user-images.githubusercontent.com/63716706/85947183-c15b2480-b966-11ea-8f1f-cfc9f88b1edf.PNG">

## 6) View the Contents of a File in HDFS  
**a.  You can use the -cat command to view text files in HDFS. Enter the following  command to view the contents of data.txt:**

<img src = "https://user-images.githubusercontent.com/63716706/85947184-c1f3bb00-b966-11ea-839b-6184bb676127.PNG">

**b. You can also use the ‐tail command to view the end of a file:**

<img src = "https://user-images.githubusercontent.com/63716706/85947185-c1f3bb00-b966-11ea-8698-e94c63e9e62f.PNG">

Notice the output this time is only the last 20 rows of data.txt.  

## 7 ) Getting a File from HDFS  
**a. See if you can figure out how to use the get command to copy test/data.txt from  HDFS into your local /tmp folder.**

<img src = "https://user-images.githubusercontent.com/63716706/85947186-c28c5180-b966-11ea-96da-9b689f322a82.PNG">

<img src = "https://user-images.githubusercontent.com/63716706/85947188-c28c5180-b966-11ea-856b-bd6c5803efb7.PNG">

## 8 ) The getmerge Command  
**a. Put the file /root/devph/labs/demos/small_blocks.txt into the test folder in  HDFS. You should now have two files in test: data.txt and small_blocks.txt.**

<img src = "https://user-images.githubusercontent.com/63716706/85947190-c324e800-b966-11ea-9d0a-d855ed68fd8f.PNG">

**Run the following getmerge command:**

**c. What did the previous command do? Did you open the file merged.txt to see what  happened?**Answer: The two files that were in the test folder in HDFS were merged into a  single file and stored on the local file system.  

## 9 ) Specify the Block Size and Replication Factor  

**a. Put /test/labs/Lab2.1/data.txt into /test/test3 in HDFS, giving it a  blocksize of 1,048,576 bytes.**

Hint:-The blocksize is defined using the dfs.blocksize property on the command line.  

**b. Run the following fsck command on data.txt:**  

**c. How many blocks are there for this file?**
Answer: The file should be broken down into two blocks. 

<img src = "https://user-images.githubusercontent.com/63716706/85947191-c324e800-b966-11ea-89ef-5c2190f69080.PNG">

















































