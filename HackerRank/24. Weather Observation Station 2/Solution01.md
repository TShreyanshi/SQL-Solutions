

```sql
SELECT ROUND(SUM(LAT_N),2), ROUND(SUM(LONG_W),2)
FROM STATION;
```

<hr/>

ROUND(number, decimals)  
***number:*** Required, The number to be rounded <br/>
***decimals:***	Optional, The number of decimal places to round number to. If omitted, it returns the integer (no decimals)
