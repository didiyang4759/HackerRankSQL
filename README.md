# HackerRankSQL

# Easy

### 1.  Revising the Select Query I
Query all columns for all American cities in the  **CITY**  table with populations larger than  `100000`. The  **CountryCode**  for America is  `USA`.
```
select * from CITY
where Population > 100000 and CountryCode = 'USA';
```
### 2. Revising the Select Query II
Query the **NAME** field for all American cities in the **CITY** table with populations larger than `120000`. The _CountryCode_ for America is `USA`.
```
select Name from CITY
where Population > 120000 and CountryCode = 'USA';
```
### 3. Query all columns (attributes) for every row in the **CITY** table.
```select * from City```

### 4. Query all columns for a city in **CITY** with the _ID_  `1661`.
```
Select * from City 
where ID = 1661; 
```
### 5. Query all attributes of every Japanese city in the **CITY** table.  The **COUNTRYCODE** for Japan is `JPN`.
```
Select * from CITY 
where COUNTRYCODE = 'JPN'; 
```
### 6.  Query the names of all the Japanese cities in the **CITY** table. The **COUNTRYCODE** for Japan is `JPN`.
```
Select name from CITY 
where COUNTRYCODE = 'JPN'; 
```
### 7. Query a list of **CITY** and **STATE** from the **STATION** table.
```
Select CITY, STATE from STATION 
```
### 8. Query a list of **CITY** names from **STATION** for cities that have an even **ID** number. Print the results in any order, but exclude duplicates from the answer.
```
/*因为要查询具有具有偶数 ID 号的城市，所以 ID%2*/
SELECT DISTINCT CITY FROM STATION WHERE (ID%2)=0
```
### 9.  Find the difference between the total number of **CITY** entries in the table and the number of distinct **CITY** entries in the table.  
The **STATION** table is described as follows:
```
select count(CITY) - count(distinct (CITY)) from STATION;
```
### 10. Query the two cities in **STATION** with the shortest and longest _CITY_ names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
-   limit N  : 返回 N 条记录
-   offset M  : 跳过 M 条记录, 默认 M=0, 单独使用似乎不起作用
-   limit N,M  : 相当于  **limit M offset N**  , 从第 N 条记录开始, 返回 M 条记录
- SELECT ... FROM ... WHERE ... ORDER BY ... LIMIT ...

```
(Select CITY, length(CITY) from STATION
order by length(CITY), CITY LIMIT 1)
union 
(Select CITY, length(CITY) from STATION
order by length(CITY) DESC, CITY LIMIT 1)
```
### 11. Query the list of _CITY_ names starting with vowels (i.e., `a`, `e`, `i`, `o`, or `u`) from **STATION**. Your result _cannot_ contain duplicates.
正则表达式
REGEXP 
```
select distinct(CITY) from STATION 
where CITY REGEXP '^[aeiou]'
```

### 12. Query the list of _CITY_ names ending with vowels (a, e, i, o, u) from **STATION**. Your result _cannot_ contain duplicates.
```
select distinct(CITY) from STATION 
where CITY REGEXP '[aeiou]$'
```
### 13. Query the list of  _CITY_  names from  **STATION**  which have vowels (i.e.,  _a_,  _e_,  _i_,  _o_, and  _u_) as both their first  _and_  last characters. Your result cannot contain duplicates.
```
select distinct(CITY) from STATION 
where CITY REGEXP '^[aeiou]' and CITY REGEXP '[aeiou]$'
```
### 14. Query the list of _CITY_ names from **STATION** that _do not start_ with vowels. Your result cannot contain duplicates.
注意not位置
```
select distinct(CITY) from STATION 
where not CITY REGEXP '^[aeiou]';
```
### 15.Query the list of _CITY_ names from **STATION** that _do not end_ with vowels. Your result cannot contain duplicates.
```
select distinct(CITY) from STATION 
where not CITY REGEXP '[aeiou]$';
```
### 16. Query the list of _CITY_ names from **STATION** that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.
```
select distinct(CITY) from STATION 
where not CITY REGEXP '^[aeiou]' or not CITY REGEXP '[aeiou]$'
```
### 17. Query the list of _CITY_ names from **STATION** that _do not start_ with vowels and _do not end_ with vowels. Your result cannot contain duplicates.
```
select distinct(CITY) from STATION 
where not CITY REGEXP '^[aeiou]' and not CITY REGEXP '[aeiou]$'
```
### 18.  Query the  _Name_  of any student in  **STUDENTS**  who scored higher than 75 _Marks_. Order your output by the  _last three characters_  of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending  _ID_.
```
SELECT Name FROM STUDENTS 
WHERE Marks > 75 
ORDER BY RIGHT(Name, 3), ID;
```
### 19. Write a query that prints a list of employee names (i.e.: the  _name_  attribute) from the  **Employee**  table in alphabetical order.
```
SELECT Name FROM Employee
order by Name;
```
### 20. Write a query that prints a list of employee names (i.e.: the _name_ attribute) for employees in **Employee** having a salary greater than 2000 per month who have been employees for less than 10 months. Sort your result by ascending _employee_id_.
```
SELECT Name FROM Employee
Where salary > 2000 and months < 10
order by employee_id;
```
### 21. Query the smallest _Northern Latitude_ (_LAT_N_) from **STATION** that is greater than 38.7780 . Round your answer to 4 decimal places.
```
select ROUND(LAT_N,4) from STATION
where LAT_N > 38.7780
ORDER BY LAT_N LIMIT 1;
```
### 22. Query the _Western Longitude_ (_LONG_W_)where the smallest _Northern Latitude_ (_LAT_N_) in **STATION** is greater than 38.7780 . Round your answer to 4 decimal places.
```
select ROUND(LONG_W,4) from STATION
where LAT_N > 38.7780
ORDER BY LAT_N LIMIT 1;
```

## round 语法 SELECT ROUND(_column_name_,_decimals_) FROM _table_name_

