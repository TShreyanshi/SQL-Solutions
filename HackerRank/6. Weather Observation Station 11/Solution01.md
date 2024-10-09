Using REGEXP function:
> ^ for start character  
> $ for end character

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT REGEXP '^[AEIOUaeiou]' 
   OR CITY NOT REGEXP '[AEIOUaeiou]$';
```

