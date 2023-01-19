Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:    select city, country, max(totaltransactionrevenue)  
                from all_sessions
                where totaltransactionrevenue is not null
                group by country, city



Answer: city	country	max
        Sydney	Australia	358000000
        New York	Canada	67990000
        Toronto	Canada	82160000
        Tel Aviv-Yafo	Israel	602000000
        Zurich	Switzerland	16990000
        Atlanta	United States	742480000
        Austin	United States	35780000
        Chicago	United States	306000000
        Columbus	United States	21990000
        Houston	United States	38980000
        Los Angeles	United States	363000000
        Mountain View	United States	8980000
        Nashville	United States	157000000
        New York	United States	81960000
        Palo Alto	United States	305000000
        San Bruno	United States	103770000
        San Francisco	United States	61970000
        San Jose	United States	154000000
        Seattle	United States	358000000
        Sunnyvale	United States	649240000
        not available in demo dataset	United States	9960000




**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:    select country, round(avg(productquantity),0) as average_products_ordered
                from all_sessions
                where productquantity is not null
                group by country



Answer:country	average_products_ordered
                Argentina	1
                Canada	1
                Colombia	1
                Finland	1
                France	1
                India	1
                Ireland	1
                Mexico	1
                Spain	10
                United States	4





**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:    select country, sum(productquantity) as sum_productquantity, v2productcategory, totaltransactionrevenue  
                from all_sessions
                where productquantity is not null
                



Answer: country	sum_productquantity	v2productcategory
        Argentina	1	Home/Bags/Backpacks/
        Canada	1	${escCatTitle}
        Canada	1	Home/Apparel/Kid's/Kids-Youth/
        Canada	1	Home/Shop by Brand/YouTube/
        Colombia	1	Home/Apparel/Men's/Men's-T-Shirts/
        Finland	1	${escCatTitle}
        France	1	Headgear
        India	1	Apparel
        Ireland	1	Home/Bags/
        Mexico	1	(not set)
        Spain	10	${escCatTitle}
        United States	8	${escCatTitle}
        United States	10	(not set)
        United States	1	Apparel
        United States	54	Bags
        United States	1	Drinkware
        United States	2	Electronics
        United States	1	Home/Apparel/Headgear/
        United States	2	Home/Apparel/Men's/
        United States	1	Home/Apparel/Men's/Men's-Outerwear/
        United States	2	Home/Apparel/Men's/Men's-T-Shirts/
        United States	1	Home/Apparel/Women's/Women's-Outerwear/
        United States	13	Home/Nest/Nest-USA/
        United States	65	Home/Office/Notebooks & Journals/
        United States	2	Home/Shop by Brand/YouTube/
        United States	1	Lifestyle
        United States	4	Nest-USA
        United States	1	Office





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:    select country, city, sum(productquantity)  
                from all_sessions
                where productquantity is not null
                group by country, city



Answer: Argentina	not available in demo dataset	1
        Canada	not available in demo dataset	3
        Colombia	not available in demo dataset	1
        Finland	not available in demo dataset	1
        France	not available in demo dataset	1
        India	Bengaluru	1
        Ireland	Dublin	1
        Mexico	not available in demo dataset	1
        Spain	Madrid	10
        United States	(not set)	1
        United States	Ann Arbor	1
        United States	Atlanta	4
        United States	Chicago	1
        United States	Columbus	1
        United States	Dallas	1
        United States	Detroit	1
        United States	Houston	2
        United States	Los Angeles	1
        United States	Mountain View	7
        United States	New York	7
        United States	Palo Alto	1
        United States	Salem	8
        United States	San Francisco	2
        United States	San Jose	1
        United States	Seattle	1
        United States	Sunnyvale	2
        United States	not available in demo dataset	127





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:    select country, city, productrevenue, transactionrevenue  
                from all_sessions
                where transactionrevenue is not null



Answer:     country	city	productrevenue	transactionrevenue	totaltransactionrevenue
            United States	Sunnyvale	120000000	200000000	200000000
            United States	not available in demo dataset	58656666	169970000	169970000
            United States	not available in demo dataset	176400000	1015480000	1015480000
            United States	not available in demo dataset	60365000	1005500000	1005500000





