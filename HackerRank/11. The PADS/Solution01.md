Using 2 SELECT:

> <Mark>FIRST SELECT QUERY</Mark>
> > **LEFT(Occupation,1)** : Extracts the first letter of occupation  
> > **CONCAT(name,'(',left(Occupation,1),')')** :  adds name + ( + occupation_first_letter + )  
> > **Example:**
> > | NAME | OCCUPATION | RESULT |
> > | :---: | :---: | :---: | 
> > | Ashley | Proffesor | Ashley(P) |
> > | Jane | Actor | Jane(A) | 

> <Mark>SECOND SELECT QUERY</Mark>
> > **GROUP BY occupation**:  group by is used to make group wrt occupations i.e. clubing one type together, after clubbing them together  
> > **COUNT(occupation)** is an aggregate function in SQL that counts the number of non-NULL occurrences of the occupation field in a dataset  
> > **LOWER(occupation)** : prints the occupation in lowercase letters
> > **CONCAT()** : contact whatever is inside the brackets in the same order

```
SELECT CONCAT(name,'(',left(Occupation,1),')')
FROM OCCUPATIONS
ORDER BY name;
SELECT 
    CONCAT('There are a total of '  , COUNT(occupation) , ' ' , lower(occupation) , 's.')
FROM OCCUPATIONS
GROUP BY occupation
ORDER BY COUNT(occupation) ASC;
```
