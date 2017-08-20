--Lesson Plan 5

--SQL

--Name: Xavier Kleiber


1. In general, why would you even want to join tow (or more) tables together? This is a good time to think about the nature of relational algebra.
 - We need more than one table to get what we want.
 
2. Describe in your own words the output from an _inner join_.
 - Rows that match in both tables.

3. Describe in your own words the output from an _outer join_.
 - An outer join’s returns differ based on if it is LEFT, RIGHT, or FULL. A full outer join acts similar to a cross join in that all rows are returned from both tables. The difference is that when the filter from the ON clause is evaluated for non-matching rows, the missing element is returned as NULL. A left outer join follows this model, but instead of preserving all rows from both tables, it only preserves all the rows from the left table. A right outer join is similar to the left outer join, but preserves all rows of the right table.

4. Describe in your own words the output from a _cross join_.
 - A cross join returns a Cartesian Product each row from one table is matched with every row in the other table.

5. A convenient mnemonic for remembering the various joins is "Ohio." Why is this true?
 - Ohio is higher in the middle. There is one type of cross join, one type of inner join, but three types of outer joins (left, right, full).

6. Give an example of a _composite join_.
 - An example of a composite join would be select C.name, O.number from sales.customers as C inner join sales.orders as O on customers.id=orders.custid and costomers.address != orders.shippingaddress;

7. What is the difference between the following two queries? The business problem is "How many orders do we have from each customer?"
 - The first won't because it will be counting the customers, whether they placed an order or not. The second only counts the orders that were actually placed and returns the correct results.
 
8. What might be one reason the following query does not return the column _custID_ in this query?
 - If no orders had an orderdate on or after ‘20160101’.
