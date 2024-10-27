<h3 align="center">
COALESCE
</h3>

1. The COALESCE() function in SQL Server is used to handle NULL values effectively by replacing them with user-defined values during expression evaluation.

2. All expressions within the COALESCE() function must have the same data type to ensure proper evaluation and return of values.

<hr/>

<h3 align="center">
COALESCE V/S ISNULL
</h3>


* COALESCE(): Evaluates a list of expressions and returns the first non-null value. It can handle multiple expressions and is more flexible in scenarios requiring more than two potential values.

* ISNULL(): Replaces NULL with a specified value but only supports two arguments: the expression to evaluate and the replacement value. It is generally used for simpler cases where only one NULL value needs to be replaced.

