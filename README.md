# SqlRockbusterMovieProject
Analysis for movie rental company that is global:
As a data analyst for the Rockbuster (BI) movie rental company, helped with lauch of strategy for the online video service. Load data into RDBMS, then use sql to analyze and answer business questions.
Movies that resulted in most/least revenue gain, average rental duration of all rentals, couuntries cutsomers are based in, customers with high lifetime and sales figure between geographic areas.
The sql queries and results in the attachment:
To display top five paying customers among the top ten cities customer id and sum of payment (amount) from payment table, first name and last name from customer table and city from city table.
Begin with inner join of customer id from payment and customer tables. Then inner join of address id from customer and address table. Inner join of city id from address and city tables. With the where statement list all the cities from the previous select statement of top ten cities, then group by customer id, first name, last name and city, then order by total payment from highest to lowest using descending and limit by 5.
