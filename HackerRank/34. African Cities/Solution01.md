

```sql
SELECT CITY.Name 
FROM CITY JOIN COUNTRY
WHERE CITY.CountryCode = COUNTRY.Code
and COUNTRY.Continent = 'Africa';
```
