# Select Statement
This statement is used to retrieve values from columns and rows from a table .
The statement can also retrieve values from an empty table.
The statement has the following format.

```Sql

SELECT variable FROM tablename WHERE condition

```

`SELECT`: This retrieves value 


` FROM`: Specifies which table are we selecting from


`WHERE` : Adds a condtion to the statement that if truthy returns the ___`variable`___

We can look at some commonly used Select Statements

We will be referencing from this table called MyCart


| id  | name           | category  | price  | stock_quantity | created_at           |
|-----|--------------|-----------|--------|---------------|----------------------|
|  1  | Nike Air Max  | Shoes     | 79.99  | 50            | 2025-03-20 12:30:45  |
|  2  | Adidas Hoodie | Clothing  | 45.50  | 30            | 2025-03-20 12:31:10  |
|  3  | Apple Watch   | Gadgets   | 250.00 | 15            | 2025-03-20 12:32:05  |
|  4  | Samsung Galaxy | Phones   | 699.99 | 10            | 2025-03-20 12:33:20  |


1. __Selecting All From The table__`SELECT` `*` 
This statement return all the variables that evaluate to `true` when `WHERE` is executed.

```sql
SELECT * FROM MyCart 
```
Here we are selecting from the table and providing a filtering parameter price . It will select all the elements all the table elements that satisfies the condition.


Output
| id  | name           | category  | price  | stock_quantity | created_at           |
|-----|--------------|-----------|--------|---------------|----------------------|
|  1  | Nike Air Max  | Shoes     | 79.99  | 50            | 2025-03-20 12:30:45  |
|  2  | Adidas Hoodie | Clothing  | 45.50  | 30            | 2025-03-20 12:31:10  |
|  3  | Apple Watch   | Gadgets   | 250.00 | 15            | 2025-03-20 12:32:05  |
|  4  | Samsung Galaxy | Phones   | 699.99 | 10            | 2025-03-20 12:33:20  |



2. __selecting  Column From Table__


`SELECT variable 1, varible 2 FROM table`


```sql
   SELECT name, category FROM MyCart
```


OutPut:
| name           | category  |
|--------------|-----------|
| Nike Air Max  | Shoes     |
| Adidas Hoodie | Clothing  |
| Apple Watch   | Gadgets   |
| Samsung Galaxy | Phones   |

3 . __Selecting Particular Columns__


```sql
SELECT name, category , price FROM MyCart WHERE (price>100)


```

Output:
| name           | category  | price  |
|--------------|-----------|--------|
| Apple Watch   | Gadgets   | 250.00 |
| Samsung Galaxy | Phones   | 699.99 |



The `SELECT` statement is not limited by the examples I have provided. You can Change the conditions column names, rows, etc



4. __SELECT With GROUP BY__


When using select with GROUP BY it sorts the elements with the order you specify in the GROUP BY

``` SQL
  SELECT category, SUM(price) AS total FROM MyCart GROUP BY category


  ```


  OutPut:

  | category  | total   |
|-----------|--------|
| Shoes     | 79.99  |
| Clothing  | 45.50  |
| Gadgets   | 250.00 |
| Phones    | 699.99 |



5. __SELECT With ORDER BY__

```sql

SELECT name , category, price FROM MyCart ORDER BY price


```

Output
| name           | category  | price  |
|--------------|-----------|--------|
| Adidas Hoodie | Clothing  | 45.50  |
| Nike Air Max  | Shoes     | 79.99  |
| Apple Watch   | Gadgets   | 250.00 |
| Samsung Galaxy | Phones   | 699.99 |


