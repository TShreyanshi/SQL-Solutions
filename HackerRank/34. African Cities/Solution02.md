

```sql
SELECT Name
FROM CITY 
WHERE CountryCode IN (SELECT COUNTRY.Code FROM COUNTRY WHERE COUNTRY.Continent = 'Africa' );
```
