# Querying database

  1. Most basic task in SQL is to query the database 


# Query using SELECT

  2. Using 'SELECT' is the beginning of simple to complex clauses used to fetch
     data
  
  3. An object model or a table is established for each type of data you want to
     organize data. 

     a. A 'user' table will store all fields and data pertaining to user such
     username, password, Ids, emails, addresses etc. 

  4. We will be using 'SELECT' on a field from a table within the database 

    e.g 
    SELECT userID FROM user;

      a. We retrieving all user entries but only the userId from all users

    SELECT * from user;

      a. '*' indicates all fields so we are returning all fields from table 'user'

    SELECT username, email, address FROM user

      a. retrieves all users and their username, email and addresses

  5. We can concatenate fields we return using '||' between field names 

    e.g
    SELECT first_name || ' ' || last_name, email FROM user;

      a. returns a list of users with a combined first and last name alont with email

      b. sample entry will look list this 'John Dode', jon@john.com

      c. Combined first and lastname in entry

  6. You can perform expressions when neccesary

    e.g
    SELECT age * 3 FROM user;

      a. returns age of every user multiplied by 3

# Column Aliases

  1. you can designate a specific name for any particular field you are
     returning 

    e.g
    SELECT first_name || ' ' || last_name as full_name FROM user;

      a. Here we are concatenating first name and last name and assigning them
      to full_name 

    e.g
    SELECT first_name || ' ' || last_name as "full name" FROM user;

      a. Same as the previous example but you have to wrap in double qoutes when 
      there are spaces between the variables

# Order by

  1. You can can return fields in a sorted format using 'ACS' or DESC after the
     field you wish to sort
  
    e.g
    SELECT first_name, last_name FROM user ORDER BY first_name ASC

      a. We are returning list of users, their first and last name specfically in the order of ascending last name which is 'a to z'.

      b. You can omit 'ASC' because it orders by ascending order by default. You will need to add DESC for theat very reason if you wish to sort by descending order

  2. In less common cases, you might see sorting for multiple fields at once. It
     will priorites the first mentioned sort and then for values that are the
     same for the first column, the second column mentioned will then sort based
     on second mentioned sort 

      e.g
      SELECT first_name, last_name FROM customer ORDER BY first_name ASC,
      last_name DESC;

        a. We see that when list is retrieved, we first sort in ascending order
        by first name. There might be multiple same first names. To further sort
        these entries, we sort those by last name in descending order 'z to a'

  3. Built in function like LENGTH() which coutns the length of string, can be
     used in these byes of queriest 

    e.g
    SELECT first_name, LENGTH(first_name) len FROM user ORDER BY len DESC

      a. It returns list of first_names, the length of those names set in
      variable 'len' and then in a reverse order '100 to 0' by'name' length
  
  4. Sometimes you have missing data which is represent by 'null'. You can
     return null at the top or bottom of the list using 'NUllS FIRST' or 'NULL
     LAST' respectively. 


    e.g 
    SELECT age FROM user ORDER BY age DESC NULLS LAST

      a. returns list of age of all users, order in reverse by the age and null
      values are pushed to the end of the list

# Using 'DISTINCT' keyword

  1. Used in the SELECT statement to remove duplicate rows from a result set. 

  2. Good when you want to see what the unique values are for a field 

    e.g
    SELECT DISTNCT favarite_color FROM user ORDER BY favorite_color

      a. retrieve user's favorite color in ascending order but each unique value only show once on the list even though there are obviously many users that wil have the same favority color.

  3. You can add multiple fields, it will account for all fields when
     determining if the entry has already been repeated. Therefore if one of the
     fields are the same, it will return but if all fields that are selected are
     the same, it will skip that entry

      e.g SELECT DISTINCT favorite_food, favorite_color FROM user;

        a. both favorite_food and favorite_color has to be repeated by same
        entry before it is skipped

      e.g SELECT DISTINCT ON (favorite_color) favorite_color, favorite_food FROM
      user ORDER BY favorite_color

        a. Returns two columns but but only for fields which the value favorite
        color is unique and ordered by favorite_color

  