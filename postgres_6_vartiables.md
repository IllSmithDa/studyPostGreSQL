# Overview of PostgreSQL data types

  1. Boolean - true or false

  2. also includes  0 and 1 with 1 being true, 

  3. yes and no,

  4. t and f 

# Character types such as char, varchar, and text.

  1. CHAR(n) is the fixed-length character with space padded. If you insert a string that is shorter than the length of the column, PostgreSQL pads spaces. If you insert a string that is longer than the length of the column, PostgreSQL will issue an error.

  2. VARCHAR(n) is the variable-length character string.  With VARCHAR(n), you can store up to n characters. PostgreSQL does not pad spaces when the stored string is shorter than the length of the column.

  3. TEXT is the variable-length character string. Theoretically, text data is a character string with unlimited length.

# Numeric types such as integer and floating-point number.

  1. Small integer ( SMALLINT) is 2-byte signed integer that has a range from -32,768 to 32,767.

  2. Integer ( INT) is a 4-byte integer that has a range from -2,147,483,648 to 2,147,483,647

  3. Serial is the same as integer except that PostgreSQL will automatically generate and populate values into the SERIAL column. This is similar to AUTO_INCREMENT column in MySQL or AUTOINCREMENT column in SQLite.

# Temporal types such as date, time, timestamp, and interval

  1. TIMESTAMPstores both date and time values.
    
  2. TIMESTAMPTZ is a timezone-aware timestamp data type. It is the abbreviation for timestamp with the time zone.

  3. INTERVAL stores periods of time.

# UUID for storing Universally Unique Identifiers

  1. The UUID data type allows you to store Universal Unique Identifiers defined by RFC 4122 . The UUID values guarantee a better uniqueness than SERIAL and can be used to hide sensitive data exposed to the public such as values of id in URL

# Array for storing array strings, numbers, etc.

# JSON stores JSON data

# hstore stores key-value pair

# Special types such as network address and geometric data.

  1. box– a rectangular box.
    
  2. line – a set of points.
    
  3. point– a geometric pair of numbers.
    
  4. lseg– a line segment.
    
  5. polygon– a closed geometric.
    
  6. inet– an IP4 address.
    
  7. macaddr– a MAC address.