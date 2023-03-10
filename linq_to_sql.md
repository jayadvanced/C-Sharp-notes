# Linq to SQL

<img src="images\linq_to_sql.png" alt="Linq to SQL">

## how to create file

- First create windows Form application 

## how to add database

project right side -> right click -> add -> new item -> left side -> Data -> service based Database 

## how to Create Table

- go to view -> server Explorer 
- right click -> add new table

```
CREATE TABLE [dbo].[Student]
(
	[Id] INT NOT NULL PRIMARY KEY identity, 
    [name] VARCHAR(50) NOT NULL, 
    [gender] VARCHAR(50) NOT NULL, 
    [age] INT NOT NULL, 
    [standard] INT NOT NULL,
)
```
- to create table -> click update -> update database

go to server explorer -> go to show table data

right cilck on right side solution explorer -> add -> Linq to sql classes

make dbml file name as database name

- Dbml stands for database markup language
