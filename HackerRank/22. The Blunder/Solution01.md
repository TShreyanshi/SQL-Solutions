```

select CEIL(AVG(salary)-AVG(REPLACE(salary,0,''))) as Error 
from employees;

```


1. CEIL : To get the amount of error rounded to the nearest integer.
2. REPLACE(salary,0,'') : Can be used with integers too, 4025 becomes 425 (0 is omitted or can say replace by nothing)
