Using REGEXP function:
> To select unique name, Use DISTINCT
>> The ^ character inside the regular expression denotes the start of the string.  
>> The $ character inside the regular expression denotes the end of the string.
>> . denotes any character, * dentoes any number of, so .* implies any number of characters can come in between 

```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[aeiouAEIOU].*[aeiouAEIOU]$';
```
