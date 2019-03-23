## SQL

This document will be a summary/cheatsheet of what I've learned about SQL.

SQL, or Structure Query Language, is used to communicate with databases. As such, implementations and use-cases will require interaction with a database. For the purposes of learning, one can install XAMPP (open source software that runs a local Apache server which can then load a mySQL module). Actual datafiles can then be downloaded from Kaggle or other related websites.

In SQL, a *Statement* is a single command sent to the database to initiate a transaction. It is made up of several *Clauses*, which may contain *Predicates* or *Expressions*. *Predicates* specify conditions that can be evaluated to SQL as boolean values, while *Expressions* produce scalars or tables of values  

Each *Statement* must be terminated with a semicolon *;* 

#### Select command

The SELECT query is one of the fundamental clauses of SQL. It tells the database what you're interested in.

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
result:
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
result:
```

| name      |
| --------- |
| Katherine |
| Andrew    |

If we wanted to find out the number of datapoints we had in the table, we can utilize the **COUNT()** method

```sql
>>> SELECT COUNT(*)
>>> FROM people;
result: 3
```

To get the count of unique values, we utilize the **DISTINCT** modifier again

```sql
>>> SELECT COUNT(DISTINCT name)
>>> FROM people;
result: 2
```

#### Filtering

The **Where** command can be used to filter records that are quantities, such as ages or years. 

Using the same database as above, 

```sql
>>> SELECT *
>>> FROM people
>>> WHERE age < 30;
result:
```

| id   | name      | age  | height | weight |
| ---- | --------- | ---- | ------ | ------ |
| 1    | Katherine | 20   | 160    | 57     |

Similarly, it can also be used to filter text results.

```sql
>>> SELECT *
>>> FROM people
>>> WHERE name = 'Andrew';
result:
```

| id   | name      | age  | height | weight |
| ---- | --------- | ---- | ------ | ------ |
| 2    | Andrew    | 50   | 180    | 85     |
| 3    | Andrew    | 43   | 172    | 98     |

If you have more than one condition, the **AND** keyword can be used to combine multiple conditions.

```sql
>>> SELECT *
>>> FROM people
>>> WHERE name = 'Andrew'
>>> AND age < 50
>>> AND age > 30;
result:
```


| id   | name      | age  | height | weight |
| ---- | --------- | ---- | ------ | ------ |
| 3    | Andrew    | 43   | 172    | 98     |

Note that you have to specify column for which the condition is to be applied on after every keyword.

For situations which require one of two or more conditions to be satisfied, the **OR** clause can be used.

```sql
>>> SELECT * 
>>> FROM people
>>> WHERE (age > 30 and height = 180)
>>> OR (NAME <> 'Andrew');
result:
```

| id   | name      | age  | height | weight |
| ---- | --------- | ---- | ------ | ------ |
| 1    | Katherine | 20   | 160    | 57     |
| 2    | Andrew    | 50   | 180    | 85     |
| 3    | Andrew    | 43   | 172    | 98     |

As always, it is good practice to wrap your logic conditions with brackets.