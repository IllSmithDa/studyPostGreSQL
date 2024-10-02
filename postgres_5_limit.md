
# LIMIT usaage

  1. LIMIT is an optional clause of the SELECT statement that constrains the number of rows returned by the query.
  
# Example of using LIMIT
SELECT username FROM user ORDER BY username LIMIT row_count

  1. we can pretend the row_count is set by qeuery itself and if row_count = 4, only first four entries will return 

# OFFSET

  1. OFFSET will skip a number or rows or entries depending on the value that is geven 

# Example of using OFFSET
SELECT username FROM user ORDER BY username OFFSET offset_count

  1. if offset_count is set to 3, it will skip the first three entries 

# Combining both OFFSET and LIMIT

  1. You can combine both keywords to further specific the rows you want to return 

# Example using OFFSET and LIMIT
SELECT username FROM user OFFSET 3 LIMIT 4

  1. returns username list from user table but will skip first 3 entries and return the next 4 entries. 

# Complex Case

  1. You can combine many different other filters like 'ORDER BY' and 'WHERE'

# Example of Combining Filters
SELECT username FROM user WHERE username LIKE 'A%' ORDER BY username OFFSET 4 LIMIT 10;

  1. This is will retrieve username list from user table if username starts with 'A', ordered alphabetically and skips the first 3 and limit to 10 rows 

# FETCH Keyword

  1. 'FETCH' is functionally equivalent to LIMIT and is more compatible with other database systems 

# Example of using FETCH 
SELECT username FROM user ORDER BY username FETCH FIRST 5 ROW ONLY
       
  1. retrieves the first five rows of list of username form table user
     
# Example Two of using FETCH
SELECT username FROM user ORDER BY username FETCH FIRST ROW ONLY
      
  1. Retrieves only the first row. Can explicity include '1' between 'FIRST' and 'ROW' if you want to explicity inclue number