# Overview of PostgreSQL data types

  1. Boolean - true or false

    a. also includes  0 and 1 with 1 being true, 

    b. yes and no,

    c. t and f 

  2. Character types such as char, varchar, and text.

    a. CHAR(n) is the fixed-length character with space padded. If you insert a string that is shorter than the length of the column, PostgreSQL pads spaces. If you insert a string that is longer than the length of the column, PostgreSQL will issue an error.

    b. VARCHAR(n) is the variable-length character string.  With VARCHAR(n), you can store up to n characters. PostgreSQL does not pad spaces when the stored string is shorter than the length of the column.

    c. TEXT is the variable-length character string. Theoretically, text data is a character string with unlimited length.

  3. Numeric types such as integer and floating-point number.

    a. Small integer ( SMALLINT) is 2-byte signed integer that has a range from -32,768 to 32,767.

    b. Integer ( INT) is a 4-byte integer that has a range from -2,147,483,648 to 2,147,483,647

    c. Serial is the same as integer except that PostgreSQL will automatically generate and populate values into the SERIAL column. This is similar to AUTO_INCREMENT column in MySQL or AUTOINCREMENT column in SQLite.

  4. Temporal types such as date, time, timestamp, and interval

    a. TIMESTAMPstores both date and time values.
    
    b. TIMESTAMPTZ is a timezone-aware timestamp data type. It is the abbreviation for timestamp with the time zone.

    c. INTERVAL stores periods of time.

  5. UUID for storing Universally Unique Identifiers

    a. The UUID data type allows you to store Universal Unique Identifiers defined by RFC 4122 . The UUID values guarantee a better uniqueness than SERIAL and can be used to hide sensitive data exposed to the public such as values of id in URL

  6. Array for storing array strings, numbers, etc.

  7. JSON stores JSON data

  8. hstore stores key-value pair

  9. Special types such as network address and geometric data.

    a. box– a rectangular box.
    
    b. line – a set of points.
    
    c. point– a geometric pair of numbers.
    
    d. lseg– a line segment.
    
    e. polygon– a closed geometric.
    
    f. inet– an IP4 address.
    
    g. macaddr– a MAC address.