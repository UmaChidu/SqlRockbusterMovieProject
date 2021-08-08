# SqlRockbusterMovieProject
Analysis for movie rental company that is global
1) SELECT COUNT(customer_id) AS customer_count, D.country
FROM customer A
INNER JOIN address B ON A.address_id = B.address_id INNER JOIN city C ON B.city_id = C.city_id
INNER JOIN country D ON C.country_id = D.country_id GROUP BY country
ORDER BY COUNT(customer_id) DESC
LIMIT 10
customer_count
60 India
53 China
36 United States
31 Japan
30 Mexico
28 Brazil
28 Russian Federation 20 Philippines
15 Turkey
14 Indonesia
To list the top ten countries in terms of customer numbers, started with customer table to get the customer id as a count and country from country table to be the display columns. Do an inner join with address table with the address_id on both tables. Next inner join with city table with city_id from city and address table. Last inner join of country and city table with country_id. Then group by country and order by customer count descending.
2) SELECT COUNT(customer_id) AS customer_count, C.city, D.country
FROM customer A
INNER JOIN address B ON A.address_id = B.address_id
INNER JOIN city C ON B.city_id = C.city_id
INNER JOIN country D ON C.country_id = D.country_id
WHERE country IN ('India', 'China', 'United States', 'Japan', 'Mexico', 'Brazil', 'Russian Federation', 'Philippines', 'Turkey', 'Indonesia')
GROUP BY city, country
ORDER BY COUNT(customer_id) DESC
LIMIT 10
country
customer_count city
2 Aurora 1 Atlixco
1 Xintai 1 Adoni Dhule
1 (Dhulia) 1 Kurashiki 1 Pingxiang 1 Sivas
1 Celaya
So
1 Leopoldo
country United States Mexico China
India
India Japan China Turkey Mexico
Brazil
To display the top ten cities within the top ten countries, started with customer id from customer table, city from city table and country from country table. Inner join on address id between customer and address tables. Then inner join of city within address and city tables. Continue with inner join of country id between city and country tables. List the top ten countries using the where statement, then group by city then country. Finally order by customer count from greatest to least using descending.
3) SELECT A.customer_id, B.first_name, B.last_name, D.city, SUM(A.amount) AS total_payment
FROM payment A
INNER JOIN customer B ON A.customer_id = B.customer_id
INNER JOIN address C ON B.address_id = C.address_id
INNER JOIN city D ON C.city_id = D.city_id
WHERE city IN ('Aurora', 'Atlixco', 'Xintari', 'Adoni', 'Dhule(Dhulia)', 'Kurashiki', 'Pingxiang', 'Sivas', 'Celaya', 'So Leopoldo')
GROUP BY A.customer_id, first_name, last_name,city
ORDER BY total_payment DESC
LIMIT 5
customer_id first_name 84 Sara
518 Gabriel 587 Sergio 537 Clinton 367 Adam
last_name Perry Harder Stanfield Buford Gooch
city total_payment Atlixco 128.7 Sivas 108.75 Celaya 102.76 Aurora 98.76 Adoni 97.8

To display top five paying customers among the top ten cities customer id and sum of payment (amount) from payment table, first name and last name from customer table and city from city table.
Begin with inner join of customer id from payment and customer tables. Then inner join of address id from customer and address table. Inner join of city id from address and city tables. With the where statement list all the cities from the previous select statement of top ten cities, then group by customer id, first name, last name and city, then order by total payment from highest to lowest using descending and limit by 5.
