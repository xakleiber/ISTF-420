--Lesson Plan 6

--SQL

--Name: Xavier Kleiber

1. What is a table expression? Can you give a technical definition of a table expression?
 - A table expression is a named query expression that represents a valid relational table. You can use table expressions in data-manipulation statements much like you use other tables.
 
2. In what SQL clause are derived tables (table valued subqueries) located?
 - Using the from clause.
 
3. Why can you refer to column aliases in an outer query that you defined in an inner table valued
subquery?
 - It thinks it is a table.

4. What SQL key word defines a common table expression?
- With

5. When using common table expressions, can a subsequent derived table use a table alias declared in a
preceding table expression?
 - Yes.
 
6. Can a main query refer to a previously defined common table expression by multiple aliases?
 - Yes.
 
7. In SQL, is a view a durable object?
 - Yes.
 
8. In a view, what does WITH CHECK OPTION do? Why is this important?
 - Prevents modifications through the view that conflicts with the view’s filter. It prevents using the view to make modifications that won't return.

9. In a view, what does SCHEMABINDING do? Why is this important?
 - Binds the schema of referenced objects and columns to the schema of the referencing object.

10. What is a table valued function?
 - Reusable table expressions that support input parameters.

11. What does the APPLY operator do?
 - It applies one table to another.
 
12. What are the two forms of the APPLY operator? Give an example of each.
 - The two forms of the APPLY operator are CROSS APPLY and OUTER APPLY.
 
 SELECT C.custid, A.orderid, A.orderdate
FROM Sales.Customers AS C
  CROSS APPLY
    (SELECT TOP (3) orderid, empid, orderdate, requireddate
     FROM Sales.Orders AS O
     WHERE O.custid = C.custid
     ORDER BY orderdate DESC, orderid DESC) AS A;
     
     SELECT C.custid, A.orderid, A.orderdate
FROM Sales.Customers AS C
  OUTER APPLY
    (SELECT TOP (3) orderid, empid, orderdate, requireddate
     FROM Sales.Orders AS O
     WHERE O.custid = C.custid
     ORDER BY orderdate DESC, orderid DESC) AS A;
