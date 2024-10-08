Using REGEXP function:
> To select unique name, Use DISTINCT
>> The ^ character inside the regular expression denotes the start of the string.

```
select DISTINCT city from station
where city NOT REGEXP '^[aeiou]';
```
