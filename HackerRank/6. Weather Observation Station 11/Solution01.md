Using REGEXP function:
> ^ for start character  
> $ for end character  
> . for any 1 character  
> .* for multiple number of any characters

```
select distinct city
from station
where city NOT REGEXP '^[aeiou].*[aeiou]$';
```

> NOTE!!!  
> For this question, Hackerrank handles the case sensitivity
