

```sql
SELECT w.id, wp.age, w.coins_needed, w.power
FROM Wands w
JOIN Wands_Property wp ON w.code = wp.code
WHERE wp.is_evil = 0
  AND w.coins_needed = (
      SELECT MIN(w2.coins_needed)
      FROM Wands w2 JOIN Wands_Property wp2
      ON w2.code = wp2.code
      WHERE wp2.is_evil = 0
        AND wp2.age = wp.age
        AND w2.power = w.power
    )
ORDER BY w.power DESC, wp.age DESC;
```

<hr/>

1. Main Query:
    * Table Aliases: The main tables are ```Wands``` (aliased as ```w```) and ```Wands_Property``` (aliased as ```wp```).
    * JOIN: ```Wands``` and ```Wands_Property``` are <Mark>joined</Mark> on ```code```, which is assumed to be a common column that links each wand with its properties.
    * Filter for Non-Evil Wands: ```WHERE wp.is_evil = 0``` filters out all wands that are considered evil.
  
2. Correlated Subquery:
    * Purpose: The subquery ensures that only the wands with the minimum coins_needed are selected for each combination of ```age``` and ```power```.
    * Conditions:<br/>
        ```wp2.is_evil = 0:``` Only non-evil wands are considered in the subquery. <br/>
        ```wp2.age = wp.age and w2.power = w.power:``` These conditions match the age and power of each wand in the main query.
    * Minimum Coins Needed: The subquery returns the minimum ```coins_needed``` for wands with the same age and power. The ```w.coins_needed = (...)``` condition in the main query ensures that only the wands with this minimum value are selected.

3. Ordering:
    The final result is ordered by power in descending order, followed by age in descending order. This means that wands with higher power come first, and within the same power level, wands with higher age are prioritized.
