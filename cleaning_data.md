What issues will you address by cleaning the data?

1. In all_sessions table, there is null values in columns susch as productrefundamount, itemquantity, itemrevenue, searchkeywords

2. The unit cost in the data needs to be divided by 1,000,000.


Queries:
Below, provide the SQL queries you used to clean your data.

1.  ALTER TABLE all_sessions
    DROP COLUMN productrefundamount, itemquantity, itemrevenue, searchkeywords;


2.  select (unit_price/1000000) as unit_price from analytics
    UPDATE analytics
    SET unit_price = unit_price/1000000
