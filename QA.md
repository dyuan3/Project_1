What are your risk areas? Identify and describe them.
There are a lot of null values among these tables. It will affect the data analyzing results.


QA Process:
Describe your QA process and include the SQL queries used to execute it.

Using left join and right join to check if there is any null vaules between these tables.

SELECT * FROM 
(SELECT name, productsku FROM products p LEFT JOIN sales_by_sku b on p.sku = b.productsku) sub 
WHERE sub.productsku is not NULL 

SELECT * FROM 
(SELECT name, productsku FROM products p RIGHT JOIN sales_by_sku b on p.sku = b.productsku) sub 
WHERE sub.productsku is not NULL 