# SQL Study

Material de estudo para SQL Language"<i class="fa fa-book fa-fw"></i> Study Book".




## Lesson 1: Select Queries

To retrieve data from a SQL database, you need to write SELECT statements  - *queries*

```
SELECT colun, another column
FROM name of the table;
```

To select all table without any column specification, you can use 

```
SELECT * 
```

It's means that you're selecting all the table

## Lesson 2: Queries with constraints

To filter certain results from being returned, you need to use a WHERE clause in the query. The clause is applied to each row of the data by check the specific column values to determine whathever you want

```
WHERE condition
    AND/OR another condition
```

You can do more complex clauses by joining logical keywords like OR r AND. Also, we have a lot of logical specification that can be used



| Operator | Condition| 
| -------- | -------- |  
| =, !=, < <=, >, >=   | Standard numerical operators
Betwenn ... AND ...| It's a range between two values
IN| Verify if something exists in a list
NOT IN | Verify if something doesn't exist in a list


It's very important to use them 'cause sometimes you have to consult queries 

## Lesson 3: Queries with constrains (Pt 2)

When you have a text data, SQL supports a lot of useful operators to do things.

| Operator | Condition| 
| -------- | -------- |  
=|Exact string comparasion
!= or <> | Inequality comparasion
LIKE | Case insensitive comparasion
NOT LIKE | Case insensitive string comparasion
%| LIKE %something%, part of a string comparasion
-| Used to match a single character
IN | String existis in a list
NOT IN | Not exist in a lit

For example:
```
WHERE column LIKE "%something%"
```

## Lesson 4: Filtering and sorting query results

The DISTINCT keyword will remove duplicate rows. Also, to help the ordering of your data, SQL provides a way to sort your results by given a column in **ASCENDING or DESCENDING** order using the **ORDER BY**

```
WHERE condition
    ORDER BY column ASC/DESC;
```

Another clause that's is commonly used with the ORDER BY are the LIMIT and OFFSET clauses. They are very helpful to optimizate your query results.

The LIMIT will reduce the number of rows to return, and the OFFSET will specify where to begin the counting the number of rows.

```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
    ORDER BY column ASC/DESC
    LIMIT num_limit OFFSET num_offset;
```

## Lesson 6: Multi-table queries with JOINs

Using the **JOIN** clause in a query, you can combine data across two separate tables using this unique key


```
SELECT column
FROM mytable
INNER JOIN another_table 
    ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

### Types of JOINS

* INNER JOIN: It atches rows from the first table and the second which have the same key that is defined by the **ON** 
* LEFT JOIN: Keeping rows in A regardless of whether a match is funf in B
* RIGHT JOIN: Keeping rows in B regardless of whether a match is found in A
* FULL JOIN: The rows of the both tables are kept, regardless of whether a matching row exist.