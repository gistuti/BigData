1. Download the files using wget command in the terminal and unzip the file as done in the Day 1 lab work.Then create a directory using-

hdfs dfs -mkdir salarydata



2.Go to the directory of the file to be exported.

.........



3.Put the data of file in the directory.

.........



4.Verify whether the data in the directory.

.......



5. Create a database in the workbench and create table salaries2 using Lab 3.2 sql queries.



.......



6. Now export the data using the sqoop command.

sqoop export --connect jdbc:mysql://(endpoint value of rds made on aws/name of the database) --username (your username) --password (your password)  --table salaries2 --export-dir salarydata --input-fields-terminated-by ","

.........



7.Now verify the data which is now exported to the mysql database using sqoop.

