<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250" align="right">

# Project Summary

In this project we will be practicing inserting and querying data using SQL. We'll make use of a handy online tool provided by DevMountain that will allow us to write SQL online. <a href="https://postgres.devmountain.com/">Click me</a>

On the left are the Tables with their fields, the right is where we will be writing our queries, and the bottom is where we will see our results.  

Any new tables or records that we add into the database will be removed after you refresh the page.

Use [www.sqlteaching.com](http://www.sqlteaching.com/) or [sqlbolt.com](http://sqlbolt.com/) as resources for the missing keywords you'll need.

## Table - People

### Instructions
1. Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color. 
    * id should be an auto-incrementing id/primary key - Use type: SERIAL

create table person (person_id serial, name varchar(254), age integer, height integer, city varchar(254), favorite_color varchar(254))

2. Add 5 different people into the person database. 
    * Remember to not include the person_id because it should auto-increment.

insert into person (name, age, height, city, favorite_color)
values ('name', age, height, 'city', 'color'), 
('name', age, height, 'city', 'color'),
('name', age, height, 'city', 'color'), 
('name', age, height, 'city', 'color'), 
('name', age, height, 'city', 'color')

3. List all the people in the person table by height from tallest to shortest.

select *
from person
order by height desc

4. List all the people in the person table by height from shortest to tallest.

select *
from person
order by height asc

5. List all the people in the person table by age from oldest to youngest.

select *
from person
order by age desc

6. List all the people in the person table older than age 20.

select *
from person 
where age > 20

7. List all the people in the person table that are exactly 18.

select *
from person
where age = 18

8. List all the people in the person table that are less than 20 and older than 30.

select *
from person
where age < 20 or age > 30

9. List all the people in the person table that are not 27 (Use not equals).

select *
from person
where age != 27

10. List all the people in the person table where their favorite color is not red.

select *
from person
where favorite_color != 'red'

11. List all the people in the person table where their favorite color is not red and is not blue.

select *
from person
where favorite_color != 'red' and favorite_color != 'blue'

12. List all the people in the person table where their favorite color is orange or green.

select *
from person
where favorite_color = 'orange' or favorite_color = 'green'

13. List all the people in the person table where their favorite color is orange, green or blue (use IN).

select *
from person
where favorite_color in ('orange', 'green', 'blue')

14. List all the people in the person table where their favorite color is yellow or purple (use IN).

select *
from person
where favorite_color in ('yellow', 'purple')

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
CREATE TABLE person ( person_id SERIAL, name VARCHAR(200), age INTEGER, height INTEGER, city VARCHAR(200), favorite_color VARCHAR(200) );
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
INSERT INTO person ( name, age, height, city, favorite_color ) VALUES ( 'First Last', 21, 182, 'City', 'Color' );
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT * FROM person ORDER BY height DESC;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM person ORDER BY height ASC;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT * FROM person ORDER BY age DESC;
```

</details>

<details>

<summary> <code> #6 </code> </summary>

```sql
SELECT * FROM person WHERE age > 20;
```

</details>

<details>

<summary> <code> #7 </code> </summary>

```sql
SELECT * FROM person WHERE age = 18;
```

</details>

<details>

<summary> <code> #8 </code> </summary>

```sql
SELECT * FROM person WHERE age < 20 OR age > 30;
```

</details>

<details>

<summary> <code> #9 </code> </summary>

```sql
SELECT * FROM person WHERE age != 27;
```

</details>

<details>

<summary> <code> #10 </code> </summary>

```sql
SELECT * FROM person WHERE favorite_color != 'red';
```

</details>

<details>

<summary> <code> #11 </code> </summary>

```sql
SELECT * FROM person WHERE favorite_color != 'red' AND favorite_color != 'blue';
```

</details>

<details>

<summary> <code> #12 </code> </summary>

```sql
SELECT * FROM person WHERE favorite_color = 'orange' OR favorite_color = 'green';
```

</details>

<details>

<summary> <code> #13 </code> </summary>

```sql
SELECT * FROM person WHERE favorite_color IN ( 'orange', 'green', 'blue' );
```

</details>

<details>

<summary> <code> #14 </code> </summary>

```sql
SELECT * FROM person WHERE favorite_color IN ( 'yellow', 'purple' )
```

</details>

</details>

## Table - orders

### Instructions

1. Create a table called orders that records: person_id, product_name, product_price, quantity.

create table orders (
    person_id serial,
  product_name varchar(254),
  product_price integer,
  quantity integer
)

2. Add 5 orders to the orders table.
    * Make orders for at least two different people.
    * person_id should be different for different people.

    insert into orders (product_name, product_price, quantity)
    values ('product_name', product_price, quantity),
    ('product_name', product_price, quantity),
    ('product_name', product_price, quantity),
    ('product_name', product_price, quantity),
    ('product_name', product_price, quantity)



3. Select all the records from the orders table.

select *
from orders

4. Calculate the total number of products ordered.

select sum(quantity)
from orders

5. Calculate the total order price.

select sum(product_price * quantity)
from orders

6. Calculate the total order price by a single person_id.

select sum(product_price * quantity)
from orders
where person_id = 1

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
CREATE TABLE orders ( person_id SERIAL, product_name VARCHAR(200), product_price NUMERIC, quantity INTEGER );
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
INSERT INTO orders ( person_id, product_name, product_price, quantity ) VALUES ( 0, 'Product', 12.50, 2 );
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT * FROM orders;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT SUM(quantity) FROM orders;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT SUM(product_price * quantity) FROM orders;
```

</details>

<details>

<summary> <code> #6 </code> </summary>

```sql
/* The value of person_id depends on what IDs you used. Use a valid ID from your table */
SELECT SUM(product_price * quantity) FROM orders WHERE person_id = 0;
```

</details>

</details>

## Table - artist

### Instructions

1. Add 3 new artists to the artist table. ( It's already created )

insert into artist (name)
values ('name'),
('name'),
('name')

2. Select 10 artists in reverse alphabetical order.

select *
from artist
order by desc
limit 10

3. Select 5 artists in alphabetical order.

select *
from artist
order by asc
limit 5

4. Select all artists that start with the word 'Black'.

select *
from artist
where name like 'Black%'

5. Select all artists that contain the word 'Black'.

select *
from artist
where name like '%Black%'

### Solution 

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
INSERT INTO artist ( name ) VALUES ( 'artist name' );
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
SELECT * FROM artist ORDER BY name DESC LIMIT 10;
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT * FROM artist ORDER BY name ASC LIMIT 5;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM artist WHERE name LIKE 'Black%';
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT * FROM artist WHERE name LIKE '%Black%';
```

</details>

</details>

## Table - employee

### Instructions

1. List all employee first and last names only that live in Calgary.

select first_name, last_name
from employee 
where city = 'Calgary'

2. Find the birthdate for the youngest employee.

select max(birth_date)
from employee

3. Find the birthdate for the oldest employee.

select min(birth_date)
from employee

4. Find everyone that reports to Nancy Edwards (Use the ReportsTo column).
   * You will need to query the employee table to find the Id for Nancy Edwards

select *
from employee
where reports_to = 2

5. Count how many people live in Lethbridge.

select count(*)
from employee
where city = 'Lethbridge'

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
SELECT first_name, last_name FROM employee WHERE city = 'Calgary';
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
SELECT MAX(birth_date) from employee;
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT MIN(birth_date) from employee;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM employee WHERE reports_to = 2;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT COUNT(*) FROM employee WHERE city = 'Lethbridge';
```

</details>

</details>

## Table - invoice 

### Instructions

1. Count how many orders were made from the USA.

select count(*)
from invoice
where billing_country = 'USA'

2. Find the largest order total amount.

select max(total)
from invoice

3. Find the smallest order total amount.

select min(total)
from invoice

4. Find all orders bigger than $5.

select *
from invoice
where total > 5

5. Count how many orders were smaller than $5.

select count(*)
from invoice
where total < 5

6. Count how many orders were in CA, TX, or AZ (use IN).

select count(*)
from invoice
where billing_country in ('CA', 'TX', 'AZ')

7. Get the average total of the orders.

select avg(total)
from invoice

8. Get the total sum of the orders.

select sum(total)
from invoice

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

```sql
SELECT COUNT(*) FROM invoice WHERE billing_country = 'USA';
```

</details>

<details>

<summary> <code> #2 </code> </summary>

```sql
SELECT MAX(total) FROM invoice;
```

</details>

<details>

<summary> <code> #3 </code> </summary>

```sql
SELECT MIN(total) FROM invoice;
```

</details>

<details>

<summary> <code> #4 </code> </summary>

```sql
SELECT * FROM invoice WHERE total > 5;
```

</details>

<details>

<summary> <code> #5 </code> </summary>

```sql
SELECT COUNT(*) FROM invoice WHERE total < 5;
```

</details>

<details>

<summary> <code> #6 </code> </summary>

```sql
SELECT COUNT(*) FROM invoice WHERE billing_state in ('CA', 'TX', 'AZ');
```

</details>

<details>

<summary> <code> #7 </code> </summary>

```sql
SELECT AVG(total) FROM invoice;
```

</details>

<details>

<summary> <code> #8 </code> </summary>

```sql
SELECT SUM(total) FROM invoice;
```

</details>

</details>

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2017. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250">
</p>

