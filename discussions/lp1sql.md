echo on
headers on

--Lesson Plan 1

--SQL

--Name: Xavier Kleiber

1. Give an informal definition of _database_ as used in the expression "relational database management system."
 - In this sense, database refers to the software.
1. Give an informal definition of _database_ as used in the expression "Human Resources database."
 - In this sense, it refers to the data.
1. Give an informal definition of _entity_ _integrity_.
 - Every row is unique.
1. Give an informal definition of _referential integrity_.
 - Foreign keys will only have data from the referencing keys.
1. What is a _relation_ as defined in the textbook? A one word answer to this question is sufficient.
 - A set.
1. Is this table in first normal form? Why or why not? If it is not, how would you change it?
 - No. The names should be firstname and lastname and the Creds should have foreign keys pointing to them.
1. Is this table in second normal form? Why or why not? if it is not, how would you change it?
 - No. The table doesn't depend solely on the primary key.
1. Is this table in third normal form? Why or why not? If it is not, how would you change it?
 - No. A new table should be created with zip as a primary key for the city and state.
1. What is an _OLTP database_? What operations is it optimized for?
 - Online Transactional Processing databse is for data entry. Inserting, updating, and deleting data.
1. What is a _star schema_? What operations is it optimized for?
 - It is designed on a fact table whith other focal points. It's used for data analasys.
