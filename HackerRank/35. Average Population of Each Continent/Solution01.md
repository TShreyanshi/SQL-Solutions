

```sql
select country.continent , FLOOR(AVG(COALESCE(city.population,NULL,0)))
from country join city
where country.code = city.countrycode
group by country.continent;
```
