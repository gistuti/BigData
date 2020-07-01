# Day 2



## Importing of data using sqoop.text file into the mysql

1. Connect the rds created on the cloud to the workbench using endpoint ,username and password. 
Create the database in the workbench using lab3.1 sql commands.Further use the query to directly load the text file into the database as a table.
---
![workbench ](https://user-images.githubusercontent.com/63596252/86251682-cff84480-bbcf-11ea-9152-d6740d2dd1de.png)




2.Use the sqoop command to import the table into HDFS.
---
sqoop import --connect jdbc:mysql://(endpoint of rds/name of the database) --username (your username) --password (your password)  --table salaries --columns salary,age -m 1 --target-dir salaries2
![import command](https://user-images.githubusercontent.com/63596252/86251508-96273e00-bbcf-11ea-9bc8-fd6d9bd673d7.png)





3.To check whether the data is imported use :
---
![data successfull2](https://user-images.githubusercontent.com/63596252/86251532-9d4e4c00-bbcf-11ea-9356-11ef9ef61275.png)




4.For seeing the contents of the table
---
![cat command3 - Copy](https://user-images.githubusercontent.com/63596252/86251544-a17a6980-bbcf-11ea-9acb-1b315a54080e.png)



5.We will use column commands to import salary and age columns
---

![salary24](https://user-images.githubusercontent.com/63596252/86251564-a7704a80-bbcf-11ea-8ca5-f2eed77db998.png)

![CAT SALARY2 5](https://user-images.githubusercontent.com/63596252/86251604-b35c0c80-bbcf-11ea-8393-78c449803caa.png)



6.Now we will use split command to split our data on the basis of columns.
We got exception in this command so we made some changes in the workbench , right click on table and select the gender column and make collation utf8mb4.
---

![error command6](https://user-images.githubusercontent.com/63596252/86251615-b951ed80-bbcf-11ea-8d43-7c33d0fd9b58.png)

![confirming split7](https://user-images.githubusercontent.com/63596252/86251629-beaf3800-bbcf-11ea-8b83-b81a66a7e6b2.png)




7. Based on the conditions given in above command we get following result.
---
![final command](https://user-images.githubusercontent.com/63596252/86251659-c838a000-bbcf-11ea-93a6-16dba5f3d13d.png)


----------------

## Exporting of data using sqoop.

1. Download the files using wget command in the terminal and unzip the file as done in the Day 1 lab work.Then create a directory using-

hdfs dfs -mkdir salarydata



2.Go to the directory of the file to be exported.
---

![export0](https://user-images.githubusercontent.com/63596252/86248147-19926080-bbcb-11ea-9ba8-fc2d248635b4.png)



3.Put the data of file in the directory.
---

![export1](https://user-images.githubusercontent.com/63596252/86248154-1dbe7e00-bbcb-11ea-8d7c-9e7752654f21.png)



4.Verify whether the data in the directory.
---

![export2](https://user-images.githubusercontent.com/63596252/86248159-20b96e80-bbcb-11ea-9bff-84e819b7e2f0.png)



5.Create a database in the workbench and create table salaries2 using Lab 3.2 sql queries.
---

![export before 4](https://user-images.githubusercontent.com/63596252/86248177-27e07c80-bbcb-11ea-92c9-acdf2dc47126.png)


6.Now export the data using the sqoop command.
---

sqoop export --connect jdbc:mysql://(endpoint value of rds made on aws/name of the database) --username (your username) --password (your password)  --table salaries2 --export-dir salarydata --input-fields-terminated-by ","


![export 3](https://user-images.githubusercontent.com/63596252/86248171-24e58c00-bbcb-11ea-9ace-df38510ec079.png)



7.Now verify the data which is now exported to the mysql database using sqoop.
---

![after exporting5](https://user-images.githubusercontent.com/63596252/86248183-29aa4000-bbcb-11ea-8dee-fbd395e08d98.png)
