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
