## SQL

This document will be a summary/cheatsheet of what I've learned about SQL.

SQL, or Structure Query Language, is used to communicate with databases. As such, implementations and use-cases will require interaction with a database. For the purposes of learning, one can install XAMPP (open source software that runs a local Apache server which can then load a mySQL module). Actual datafiles can then be download them from Kaggle or other related websites.



#### Select command

SELECT is one of the fundamental commands of SQL. It tells the database what you're interested in.

For example, suppose we have a table called 'People' containing the following:

| id   | name      | age  |
| ---- | --------- | ---- |
| 1    | Katherine | 20   |
| 2    | Andrew    | 50   |
| 3    | Andrew    | 43   |

```mysql
>>> SELECT name 
>>> FROM people;
```

will return the column 'name' from the 'People' table

| name      |
| --------- |
| Katherine |
| Andrew    |
| Andrew    |

