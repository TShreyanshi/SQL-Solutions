### Using CASE:

* (SELECT DISTINCT P FROM BST WHERE P IS NOT NULL): It selects the distinct node from the table in column P that are not NULL
* ORDER BY N : sorts the node in ascending order  
* CASE WHEN CONDITIONS:
  1. WHEN P is NULL THEN "Root" : If the parent P of any node N is null that means it is the ROOT  
  2. WHEN N NOT IN (SELECT DISTINCT P FROM BST WHERE P IS NOT NULL) THEN "Leaf" : If the node N is not a Parent (i.e not in column P) then it is a LEAF NODE  
  3. ELSE "Inner" : If the above 2 conditions are false that means the node is a parent and and a root node so it is a INNER NODE  



```

SELECT N,
CASE
    WHEN P is NULL THEN "Root"
    WHEN N NOT IN (SELECT DISTINCT P FROM BST WHERE P IS NOT NULL) THEN "Leaf"
    ELSE "Inner"
END AS NodeType
fROM BST
ORDER BY N;

```
