
```sql
WITH challenge_count AS (
    SELECT h.hacker_id as hacker_id, h.name as name, COUNT(*) as counting
    FROM Hackers as h
    INNER JOIN Challenges as c
    ON c.hacker_id = h.hacker_id
    GROUP BY h.hacker_id, h.name
)
SELECT hacker_id, name, counting
FROM challenge_count
WHERE counting NOT IN (
    SELECT counting
    FROM challenge_count
    WHERE counting NOT IN (SELECT MAX(counting) FROM challenge_count)
    GROUP BY counting
    HAVING COUNT(*) > 1
)
GROUP BY hacker_id, name
ORDER BY counting DESC, hacker_id;
```
