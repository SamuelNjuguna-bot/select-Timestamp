# Time Stamp

What we will learn in this chapter:


- ### Viewing Current date


To perform this we use 

`SELECT now()`

This returns current date and its timezone
The same results can be achieved through this method

`SELECT CURRENT_TIMESTAMP;`

```sql
mydb=# SELECT CURRENT_TIMESTAMP;
       current_timestamp
-------------------------------
 2025-03-24 10:35:29.278435+03
(1 row)
```

Lets say you want to display date without timestamp, here is how you go about it

`SELECT now():: timestamp` or `SELECT LOCALTIMESTAMP`
result

```sql
mydb=# SELECT '2000-07-22' :: DATE + INTERVAL '24 years';
      ?column?
---------------------
 2024-07-22 00:00:00
(1 row)

```

- ### Adding Dates
Format
`SELECT date:: DATE + INTERVAL Addunit`


`date`- This is the date entry and it is a must. It has the following format `YYY-MM-DD`
`INTERVAL + DATE` - Are required keywords
`Addunit` - This is the no of years, months, hours, seconds you want to include.


We can look at an example below.


`SELECT '2000-07-22' :: DATE + INTERVAL '24 years'`

The above statement returns the column like this


```sql    
?column?
---------------------
 2024-07-22 00:00:00
(1 row)
```


- ### Checking The Time Of The Day

format
`SELECT TIMEOFDAY()`


Output

```sql
   mydb=# SELECT TIMEOFDAY();
              timeofday
-------------------------------------
 Mon Mar 24 10:51:24.686879 2025 EAT
(1 row)
```
Cheking out only the current date we use
`SELECT CURRENT_DATE;`


Output 
```sql
mydb=# SELECT CURRENT_DATE;
 current_date
--------------
 2025-03-24
(1 row)
```

For current time we use `SELECT CURRENT_TIME` and without timezone we use `SELECT LOCALTIME`


___NOTE___ :

Using CURRENT_DATE, CURRENT_TIME displays time with a time zone but using LOCALDATE, LOCALTIME displays without timezone

- ### Checking out age can use the age function
format
`SELECT AGE(timestamp '2001-15-09');`


Output:
```sql
mydb=# SELECT AGE(timestamp '2001-09-15');
          age
------------------------
 23 years 6 mons 9 days
(1 row)

```

- ### Extracting a particular date we use 
Format:


`SELECT EXTRACT(field FROM source)`

field: The day, month, year you want to extract
source: function that returns the date like now()

Example

`SELECT EXTRACT('month' FROM now());`

Output:

```sql
 extract
---------
       3
(1 row)

```


