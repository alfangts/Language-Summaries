## SQL

This document will be a summary/cheatsheet of what I've learned about SQL.

SQL, or Structure Query Language, is used to communicate with databases. As such, implementations and use-cases will require interaction with a database. For the purposes of learning, one can install XAMPP (open source software that runs a local Apache server which can then load a mySQL module). Actual datafiles can then be download them from Kaggle or other related websites.



#### Select command

SELECT is one of the fundamental commands of SQL. It tells the database what you're interested in.

For example, suppose we have a table called 'People' containing 5 fields *id*, *name*, *age*, *height* and *weight*

| id   | name      | age  | height | weight |
| ---- | --------- | ---- | ------ | ------ |
| 1    | Katherine | 20   | 160    | 57     |
| 2    | Andrew    | 50   | 180    | 85     |
| 3    | Andrew    | 43   | 172    | 98     |



```sql
>>> SELECT name 
>>> FROM people;
```

will return the column 'name' from the 'People' table

| name      |
| --------- |
| Katherine |
| Andrew    |
| Andrew    |

Suppose now we wanted their names and their ages. That can be obtained as follows

```sql
>>> SELECT name, age
>>> FROM people;
```

| name      | age  |
| --------- | ---- |
| Katherine | 20   |
| Andrew    | 50   |
| Andrew    | 43   |

Notice how there are two Andrews in the *names* column? We can query the database for **unique** values only by using the **DISTINCT** modifier.

```sql
>>> SELECT DISTINCT name
>>> FROM people;
```

| name      |
| --------- |
| Katherine |
| Andrew    |

If we wanted to find out the number of datapoints we had in the table, we can utilize the **COUNT()** method

```sql
>>> SELECT COUNT(*)
>>> FROM people;
3
```

To get the count of unique values, we utilize the **DISTINCT** modifier again

```sql
>>> SELECT COUNT(DISTINCT name)
>>> FROM people;
2
```



