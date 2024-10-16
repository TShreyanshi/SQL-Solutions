```

SELECT c.company_code,c.founder,
COUNT(distinct(l.lead_manager_code)),
COUNT(distinct(s.senior_manager_code)),
COUNT(distinct(m.manager_code)),
COUNT(distinct(e.employee_code)) 
FROM Company c JOIN Lead_Manager l 
ON c.company_code=l.company_code JOIN Senior_Manager s 
ON l.lead_manager_code=s.lead_manager_code JOIN Manager m 
ON s.senior_manager_code=m.senior_manager_code JOIN Employee e 
ON m.manager_code=e.manager_code 
GROUP BY company_code,founder 
ORDER BY c.company_code ASC;

```

<Mark>The question follows hierarchy so we can use inner join / join.</Mark>  
  
  
If it would have not followed hierarchy then :  
* Using join (inner join) would result in the only companies with all levels of management (lead, senior, regular, employees) are included. It ensures that one is counting only fully populated hierarchies.  
* Using left join would ensure all the companies, even if they’re missing some levels of management.  
  
  
### ***Conclusion:***  
If your query’s goal is to get information about all companies, even those with incomplete hierarchies, then a LEFT JOIN would be better. But if you only care about companies with complete data (all management levels present), INNER JOIN is the correct choice.
