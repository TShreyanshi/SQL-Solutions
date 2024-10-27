
### COALESCE

The COALESCE() function in SQL Server is used to handle NULL values effectively by replacing them with user-defined values during expression evaluation.

All expressions within the COALESCE() function must have the same data type to ensure proper evaluation and return of values.

``` 
COALESCE ( exv1, exv2…, exvN )
 ```

* exv1, exv2…, exvN are expression values.
* All expressions must have the same data type.
* It could have multiple expressions.

Reference: https://www.geeksforgeeks.org/use-of-coalesce-function-in-sql-server/

<hr/>

<h3 align="left">
COALESCE V/S ISNULL
</h3>


| COALESCE() | ISNULL() |
| :--- | :--- |
| Evaluates a list of expressions and returns the first non-null value. It can handle multiple expressions and is more flexible in scenarios requiring more than two potential values. | Replaces NULL with a specified value but only supports two arguments: the expression to evaluate and the replacement value. It is generally used for simpler cases where only one NULL value needs to be replaced. |

<br/>

<h3 align="left">
Example : 
</h3>

| <Mark> SELECT COALESCE(NULL, NULL, 'Third Value', 'Fourth Value') AS result; </Mark> | <Mark> SELECT ISNULL(NULL, 'Replacement Value') AS result; </Mark> |
| :--- | :--- |
| In this example, COALESCE evaluates each expression in the list and returns 'Third Value' because it's the first non-null value it encounters. This is useful when you have multiple potential sources for a value and want to default to the first available one. | Here, ISNULL checks if the first argument is null and, if so, returns 'Replacement Value'. It only supports two arguments, making it simpler but less flexible compared to COALESCE.|

<br/>

<h3 align="left">
Practical Example :
</h3>

| <Mark>SELECT id, COALESCE(contact_preference, phone, email, 'No Contact Info') AS preferred_contact FROM users;</Mark>|<Mark> SELECT id, ISNULL(phone, 'No Phone') AS phone FROM users; </Mark> |
| :--- | :--- |
| This query will return the user's preferred contact method based on their preference, falling back to phone, then email, and finally a default message if none are available. | This query will replace any null phone entries with 'No Phone'. |
