
--Lesson Plan 4

--SQL

--Name: Xavier Kleiber

1. What is a data type? Why do we have data types?
 - A particular kind of data item. Using the right data type can optimize the system.
2. What is a collation? Name four elements of a collation.
 - Collation is a property of character data, like case sensitivity and accent sensitivity.
3. How would you strip whitespace from a string? For example, suppose you had "   Dave   " but you only wanted "Dave".
 - Use a combination of LTRIM and RTRIM.
4. Suppose you wanted to make a list of every college and university that was called an Institute from the college table. Write the query.
 - select name from college where name like ‘%institute%’;
5. How would you find out the index of the first space in a string? For example, the index of the first space in "Barack Hussein Obama" would be 7.
 - CHARINDEX
6. How would you select just the first name in a list of the presidents. First names can be an arbitrary length, from "cal" to "Benjamin".
 - a combination of LEFT and CHARINDEX.
7. Payments are due exactly 30 day from the date of the last function. Write a select query that calculates the date of the next payment. Pretend we want to update a column in a database that contains the date of the next payment. We will do this when we write UPDATE queries.
 - select dateadd(day, 30, orderdate) as nextpayment from orders;
8. Suppose your son or daughter wants to run a query every day that tells them the number of days until their 16th birthday. Qrite a select query that does this.
 - select datediff(day, getdate(), dateof16thbirthday);
9. What function returns the current date? This is very useful in a table that maintains a log of events, such as user logins.
 - Getdate()
