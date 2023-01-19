Question 1: find all duplicate records

SQL Queries:    select fullvisitorid, count(fullvisitorid) from all_sessions
                group by fullvisitorid
                HAVING COUNT(fullvisitorid) > 1;

Answer: 794



Question 2: find the total number of unique visitors (`fullVisitorID`)

SQL Queries:    select fullvisitorid, count(fullvisitorid) from all_sessions
                group by fullvisitorid

Answer: 14223


Question 3: find the total number of unique visitors by referring sites

SQL Queries:    select fullvisitorid, count(fullvisitorid), timeonsite 
                from all_sessions
                where all_sessions.timeonsite is not null
                group by all_sessions.fullvisitorid, all_sessions.timeonsite

Answer: 11313



Question 4: find each unique product viewed by each visitor

SQL Queries:    SELECT fullvisitorid, v2productname, COUNT(v2productname)
                FROM all_sessions
                GROUP BY v2productname, fullvisitorid

Answer: 15115



Question 5: compute the percentage of visitors to the site that actually makes a purchase

SQL Queries:    select count(units_sold) 
                from analytics
                where units_sold is not null


Answer: 95147/4205975 = 2.26%
