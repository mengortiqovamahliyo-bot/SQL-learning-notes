# SELECT
SELECT -- mainly used to select a specific part of the database, like a column name or a row

 ```sql
 SELECT * FROM users — users is the name of the table, and it is just an example. * means all data from users
```
If you want to choose multiple columns from the database, you can use SELECT like this:
```sql
SELECT column_name, another_column_name
FROM table_name
```
# WHERE
In SQL, you can extract data according to certain demands by giving conditions using WHERE:
```sql
SELECT column_name
FROM table_name
WHERE condition --column_name > 2
```
### Conditions are written using operators below:
```
= --> if it is equal to smth
!= --> if it is not equal to smth
< --> if it is less than smth
> --> if it is more than smth
<= --> if it is less than or equal to
>= --> if it is more than or equal to
BETWEEN ... AND ... --> if it is between them(column_name BETWEEN num 1 AND num 2 )
NOT BETWEEN ... AND ... --> if it is not between them
IN() --> checks whether a value exists in a list
NOT IN() checks if a value does NOT exist inside a list. This query returns all users except those in the brackets.
```sql
SELECT *
FROM users
WHERE name NOT IN ('Ali', 'Vali');
```
# Filtering and sorting
The data can be filtered by using "Distinct", which removes duplicates:
```sql
SELECT director FROM movies;
```
```natija
Ali
Vali
Ali
Sami
```
```sql
SELECT DISTINCT director
FROM movies;
```
```natija
Ali
Vali
Sami
```
###Sorting
To sort the database alphabetically, we use:
```
SELECT title
FROM movies
ORDER BY column_name asc
```
To reverse it:
```
SELECT title
FROM movies
ORDER BY column_name DESC
```
### limit and offset
```
| id | name  |
| -- | ----- |
| 1  | Ali   |
| 2  | Vali  |
| 3  | Sami  |
| 4  | Olim  |
| 5  | Zafar |
```
```
SELECT * FROM users
LIMIT 2 OFFSET 2;
```
```
Sami
Olim
```
# Joining two tables
In real projects you have to work several databases and you have join them together. To do this you will use join.
Users 
```
| id | name |          
| -- | ---- |
| 1  | Ali  |
| 2  | Vali |
```
Orders
```
| id | user_id | product |
| -- | ------- | ------- |
| 1  | 1       | Phone   |
| 2  | 2       | Laptop  |
```


```sql
select name, product
from users
join orders
    on users.id = orders.user_id
```
# Outer Joins





















