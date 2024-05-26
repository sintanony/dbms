# Database Design and SQL Queries

Design any database with at least 3 entities and establish proper relationships between them.

## SQL Statements

```sql
-- (a) Display columns Id, Name, Population from the city table and limit results to first 10 rows only.
SELECT Id, Name, Population FROM city LIMIT 10;

-- (b) Display columns Id, Name, Population from the city table and limit results to rows 31-40
SELECT Id, Name, Population FROM city LIMIT 30, 10;

-- (c) Find only those cities from the city table whose population is larger than 2,000,000.
SELECT Name, Population FROM city WHERE Population > 2000000;

-- (d) Select the districts with population above the average population of all the districts in the table.
SELECT District FROM city WHERE Population > (SELECT AVG(Population) FROM city);

-- (e) What is the country code for Kabul?
SELECT * FROM city WHERE Name = 'Kabul';

-- (f) Find out the population and average life expectancy for people in Argentina. (ARG) is (37032000, 75.10000)
SELECT Population, AVG(LifeExpectancy) FROM country WHERE Code = 'ARG';

-- (g) Using IS NOT NULL, ORDER BY, LIMIT, what country has the highest life expectancy? (Andorra, 83.5)
SELECT * FROM country;
SELECT Name, LifeExpectancy FROM country ORDER BY LifeExpectancy DESC LIMIT 1;
