```sql
SELECT ROUND(SUM(LAT_N),4)
FROM STATION
WHERE LAT_N > 38.7800 AND LAT_n < 137.2345;
```