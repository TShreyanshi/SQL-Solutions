Using RIGHT function:
> Using Order by to sort in ascending order  
> Order by right(name,3) sorts according to the last 3 letter and then by ID

<Mark>With Sub-Query: </Mark>

```
select name from students
where name in (select name from students where marks>75)
Order by right(name,3), ID; 
```

<Mark>Without Sub-Query: </Mark>

```
select name from students
where marks>75
Order by right(name,3), ID; 
```
