# Joins 

  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-joins/

  1. You can join different fields from different tables together as one row
     using 'JOIN' keyword 

  2. There are many types of JOIN including INNER, OUTER, LEFT, RIGHT

# INNER JOIN

  1. INNER JOIN is the most basic join of joining tables based on a set of
     queries 

    e.g
    SELECT, a_fav_book, b_fav_book, a_Id, b_Id FROM users_a INNER JOIN users_b
    ON a_fav_book = b_fav_book

      a. INNER JOIN creates a new row that contains columns from both tables but
      only entries that column 'a_fav_book' value from 'users_a' and
      'b_fav_book' fromt 'users_b'. value of a_Id and b_Id do not need to match.

# LEFT, RIGHT JOIN 

  1. When talking about LEFT JOINs and RIGHT JOINS, it important to understand
     that when we are joining tables in SQL, the first table becomes the left
     table and the second mentioned table becomes the right table

  2. The first mentioend table will have every row returned and the second table
     will either return row values that match the query or the field from their
     tables wil return null.

    e.g
    SELECT, a_fav_book, b_fav_book, a_Id, b_Id FROM users_a LEFT JOIN users_b
    ON a_fav_book = b_fav_book

      a. while all columns from table 'users_a' will return its value, columns from table 'users_b' will return null unless its field b_fav_book matches a row that has b_fav_matches as the same value

    e.g
    SELECT, a_fav_book, b_fav_book, a_Id, b_Id FROM users_a LEFT JOIN users_b
    ON a_fav_book = b_fav_book WHERE b is null;

      a. while all columns from table 'users_a' will return its value, columns from table 'users_b' will return null unless its field b_fav_book matches a row that has b_fav_matches as the same value. The as before but 'WHERE b is null' means it then rejects any rows in which b is null;

# FULL OUTER JOIN

  1. The full outer join or full join returns a result set that contains all
     rows from both left and right tables, with the matching rows from both
     sides if available. In case there is no match, the columns of the table
     will be filled with NULL.
  
    e.g
    SELECT a_fav_book, b_fav_book, a_Id, b_Id FROM users_a FULL OUTER JOIN users_b
    ON a_fav_book = b_fav_book

      a. Includes all rows from the tables but if a a_fav_book doesn't have a matching b_fav_book, then a new matching column will be created for a_fav_book, which is b_fav_book with its value set to null. This prevents tables with columns that have not been assigned at all

# UNION 

  1. Combines results of two ore more SELECT statements into a single set

  2. The UNION operator may place the rows from the result set of the first
     query before, after, or between the rows from the result set of the second
     query.
  
  3. The number and the order of the columns in the select list of both queries
     must be the same.

    e.g
    SELECT a_fav_book FROM users_a UNION b_fav_book FROM users_b
  
      a. combines result of both queries together

# INTERSECT

  1. The INTERSECT operator returns any rows that are available in both result
     sets.
  
  
 