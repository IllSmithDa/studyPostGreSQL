# Where clause

  1. Used to filter rows so that only rows that meet specific conidtions are
     returned 

  2. 'WHERE' used after 'FROM' clause and before 'ORDER BY'

  3. Uses comparion operators such as '=', '>', '<=', '>=', '!=' which comparies
     enntries fields with a paritcular value

      e.g 
      SELECT last_name, first_name FROM user WHERE first_name = 'Joe'

        a. Returns a list of user's list_name and first_name but only for
        rows/entries where first_name is equal to Joe

  4. Also uses word operators such as 'AND', 'OR', 'IN', 'BETWEEN', 'LIKE', 
    'IS NULL' and 'NOT'

    e.g
    SELECT first_name, last_name FROM user WHERE first_name = 'Joe', OR 'last_name' = 'Walker';

      a. return a list of user's first_name and last_name if first_name = 'Joe' or if their 'last_name' is equal to walker

# Keyword 'IN'

  1. keyword 'IN' used to see of a field has a value from a set of values.

    e.g
    SELECT first_name, last_name FROM user WHERE first_name IN ('Alan', 'Agnie', 'Alice');

      a. returns a list of user's first_name and last_name but only for entries where first_name is either 'Alan', 'Angie' or 'Alice'

  2. You can also exclude using 'NOT IN' to ensure that value doesn't not match a
     set of values

    e.g
    SELECT userID FROM user WHERE userID NOT IN (1, 2, 3);

      a. retrieves list of userIDs from table 'user' but only rows where userID is not '1', '2' or '3'

# Keyword 'LIKE'

  1. keyword 'LIKE' used to match a specific pattern. '%' will match with any
     thing. '%' in the front matches anything that ends with particular
     characters and '%' in the back match anything that starts with those
     characters
     
     e.g 
     SELECT first_name, last_name FROM user WHERE first_name LIKE 'Ann%' AND 
     last_name LIKE '%im'

      a. returns list of user's first_name and last_name but only for users's
      whose first_name starts with 'Ann' and last name ends with 'im'

  2. You can use '%' both front and behind to indicate that it simply needs to
     have the characters in the query

     e.g 
     SELECT first_name FROM user WHERE first_name LIKE '%er%' ORDER BY
     first_name;
     
      a. Retrieves first_name list but first_name needs to have 'er' in it.
      Names like 'Erob', 'Amber' and 'Cheryl' all have 'er'. Doesnt' matter if
      its in the front or back or in the middle of the string.

  3. '_' is represents any single character. Used in combination with 'LIKE' to
     match strings

     e.g
     SELECT first_name FROM user WHERE first_name like '_o_' 

      a. Single character followed by 'o' and followed by single character.
      Matches first_names like 'Bob' and 'Joe' but not 'Roland' because there
      are too many characters after 'o' in Roland. Must be exactly one. 

    e.g 
    SELCET first_name FROM user WHERE first_name like '_her%'
    
      a. Begin with one single character, followed by 'her' and ends with any number of characrters 

# Key phrase NOT LIKE

  1. Will not return any matches using 'NOT LIKE'

    e.g
    SELECT first_name FROM user WHERE first_name NOT LIKE '_her%'

      a. Do not return any names that begin with one single char, followed by 'her' followed by any number of characters

# ILIKE keyword 

  1. If you want to ignore case sensitivety where uppercase or lowercase is
     returned as long as the letter matches, use 'ILIKE'

     e.g
     SELECT first_name FROM user WHERE first_name ILIKE 'an%'

      a. Matches any name that starts with 'an' regardless of it is uppercase
      letters like the 'A' in 'Andy', 

# Keyword 'BETWEEEN'

  1. Use 'BETWEEN' if you want to test for a range of values for a particular
     field. Note that the values that make up the edge of the range are also
     included

     e.g
     SELECT first_name FROM user WHERE LENGTH(first_name) BETWEEN 3 AND 5

      a. returns list of users where their first_name length is from 3 to 5
      which also includes names that are 3 to 5 characters long. 

  2. You can even set date ranges using between. If you want to check a value
     against of date ranges, you should use the literal date in ISO 8601 format
     i.e., YYYY-MM-DD
  
    e.g SELECT payment_date FROM payment WHERE payment_date BETWEEN '2007-02-07' AND '2007-02-15';

      a. Retrieves payment_date list if its from Feb 7th 2007 and Feb 15th 2007. The date in the ranges are included

  3. You can combine not to indicate you are matching outside of the range
     values 

     e.g
     SELECT age FROM user WHERE age NOT BETWEEN 18 AND 30 

# keyword NULL

  1. You can query database to return rows based off whether field values are null or
     not given a value

    e.g 
    SELECT phone FROM contacts WHERE phone IS NULL;

      a. retrieves a list of phone numbers from contacts table but only rows where phone number is not given or NULL

  2. You can also use 'NOT NULL' to enforce returning rows where field is given
     a values 

     e.g 
      SELECT phone FROM contacts WHERE phone IS NOT NULL;

      a. retrieves a list of phone numbers from contacts table but only rows
      where phone number has a value


# Using '<>'

  1. Use '<>' to indicate Not like or Not Equal

    e.g
    SELECT last_name FROM user WHERE last_name <> 'Doe'

      a. retrieves user last_names where last name is not Doe 

      b. you can also use '!=' to do the same thing