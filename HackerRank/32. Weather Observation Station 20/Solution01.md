

```sql
SELECT ROUND(LAT_N,4)
FROM
    ( SELECT LAT_N, 
             ROW_NUMBER() OVER (ORDER BY LAT_N) AS row_num,
             COUNT(LAT_N) OVER () AS total_rows 
             FROM STATION ) 
STATION
WHERE row_num =(total_rows + 1)/2;
```
