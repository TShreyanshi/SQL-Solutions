```sql
Select h.hacker_id, h.name , SUM(result.max_score) as totalScore
from hackers AS h
join (SELECT hacker_id, challenge_id, MAX(score) AS max_score
FROM submissions
GROUP BY hacker_id, challenge_id) AS result
ON h.hacker_id = result.hacker_id
GROUP BY h.hacker_id, h.name
HAVING totalScore > 0
ORDER BY totalScore DESC, h.hacker_id ASC;
```
