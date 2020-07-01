
1. Download the files using wget command in the terminal and unzip the file as done in the Day 1 lab work.Then create a directory using-

hdfs dfs -mkdir salarydata



2.Go to the directory of the file to be exported.

![export0](https://user-images.githubusercontent.com/63596252/86248147-19926080-bbcb-11ea-9ba8-fc2d248635b4.png)



3.Put the data of file in the directory.

![export1](https://user-images.githubusercontent.com/63596252/86248154-1dbe7e00-bbcb-11ea-8d7c-9e7752654f21.png)



4.Verify whether the data in the directory.

![export2](https://user-images.githubusercontent.com/63596252/86248159-20b96e80-bbcb-11ea-9bff-84e819b7e2f0.png)



5. Create a database in the workbench and create table salaries2 using Lab 3.2 sql queries.

![export before 4](https://user-images.githubusercontent.com/63596252/86248177-27e07c80-bbcb-11ea-92c9-acdf2dc47126.png)


6. Now export the data using the sqoop command.

sqoop export --connect jdbc:mysql://(endpoint value of rds made on aws/name of the database) --username (your username) --password (your password)  --table salaries2 --export-dir salarydata --input-fields-terminated-by ","

![export 3](https://user-images.githubusercontent.com/63596252/86248171-24e58c00-bbcb-11ea-9ace-df38510ec079.png)



7.Now verify the data which is now exported to the mysql database using sqoop.

![after exporting5](https://user-images.githubusercontent.com/63596252/86248183-29aa4000-bbcb-11ea-8dee-fbd395e08d98.png)
