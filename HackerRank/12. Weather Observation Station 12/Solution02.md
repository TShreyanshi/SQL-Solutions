Using REGEXP function:

```
select distinct city
from station
where city NOT REGEXP '^[AEIOU]'
AND city NOT REGEXP '[AEIOU]$';
```
