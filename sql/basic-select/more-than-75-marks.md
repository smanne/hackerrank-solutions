[**Solution (MySQL)**](https://www.hackerrank.com/challenges/more-than-75-marks)
```sql
SELECT Name from STUDENTS WHERE Marks > 75 ORDER BY RIGHT(Name, 3), ID
```
