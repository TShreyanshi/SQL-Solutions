

```sql
SELECT SUM(CITY.Population) AS total_population
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
WHERE COUNTRY.Continent = 'Asia';
```
