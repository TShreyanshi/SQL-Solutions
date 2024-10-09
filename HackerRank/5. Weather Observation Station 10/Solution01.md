Using REGEXP function with NOT:
> $ is used to extract the last character of city 

```
select distinct city
from station
where NOT city REGEXP '[aeiouAEIOU]$';
```
