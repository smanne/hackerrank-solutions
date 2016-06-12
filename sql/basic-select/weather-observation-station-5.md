[**Solution (MySQL)**](https://www.hackerrank.com/challenges/weather-observation-station-5)
```sql
(SELECT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY) DESC LIMIT 1) UNION
(SELECT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY) ASC LIMIT 1)
```
