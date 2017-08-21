--Lesson Plan 6

--SQL

--Name: Xavier Kleiber


1. In your own words, what is a _subquery_?
 - A query inside another query.

2. In your own words, what is a _self contained subquery_?
 - Does not depend on tables from another query.

3. In your own words, what is a _correlated subquery_?
 - Does depend on tables from other queries.

4. Give an example of a subquery that returns a single value. When would you use this kind of subquery?
 - select firstname + ' ' + lastname + ' is Employee of the Month!' as winner
  from hr.Employees
  where empid=
  (select TOP 1 empid
  from sales.orders
  group by empid
  order by count(*) desc);
  
  When you only want one result.

5. Give an example of a subquery that returns multiple values. When would you use this kind of subquery?
 -   select firstname + ' ' + lastname + ' had no sales in May, 2016.' as counsel
  from hr.Employees
  where empid NOT IN
  (select empid
  from sales.orders
  where orderdate like '2016-05%');
  
  Used to filter results.

6. Give an example of a subquery that returns table values. When would you use this kind of subquery?
 -   select OrderYear, count(distinct custid) as NumCust
  from (select year(orderdate) as OrderYear, custid
  from sales.orders) as x
  group by OrderYear;

7. What does the _exists_ predicate do? Give an example.
 -  select firstname + ' ' + lastname + ' had sales in May, 2016.' as award
  from hr.Employees e
  where exists
  (select empid
  from sales.orders o
  where e.empid=o.empid
  and orderdate like '2016-05%');
  
  Filters out ones that do not have the indicated value.

8. What happens if we use the _not_ operator before a predicate? Give an example.
 -  select firstname + ' ' + lastname + ' had no sales in May, 2016.' as counsel
  from hr.Employees e
  where not exists
  (select empid
  from sales.orders o
  where e.empid=o.empid
  and orderdate like '2016-05%');
  
  It does the exact opposite of just having _exists_.

9. When you use _exists_ or _not exists_ with respect to a row in a database, dois it return two or three values? Explain your anser.
 - Two. It is either true or false.

10. How would you write a subquery to calculate aggregates? For example, you want to calculate yearly sales of a product, and you also want to keep a running sum of total sales. Explain how you would use a subquery to do this.
 -   select orderyear as Year, qty as Sales,
  (select sum(view2.qty)
  from Sales.OrderTotalsByYear as view2
  where view2.orderyear <= view1.orderyear) as RunningSales
  from Sales.OrderTotalsByYear as view1
  order by orderyear;
  
  Query one to display the yearly sales for each year and a second for the sum of total sales.
