Using <Mark>REGEX</Mark> Function:
> Dollar ($) Symbol: It tells the computer that the match must occur at the end of the string or before \n at the end of the line or string.

```
SELECT DISTINCT city
FROM station
WHERE city REGEXP '[aeiou]$';
```
