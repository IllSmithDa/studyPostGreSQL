# INSERT 

  1. insert a row of data into a table using 'INSERT INTO'

# Example using INSERT INTO
INSERT INTO user(username, email) VALUES('sam444', 'sam@sam.com')

  1. inserting a new user with s'sam444' as its username and 'sam@sam.com' as its email

# You can specify fields you want to return after inserting using 'RETURNING' keyword
NSERT INTO user(username, email) VALUES('sam444', 'sam@sam.com') RETURNING email

  1. A Insert implenatation of user that also return email when completed 

# UPDATE 

  1. You can update database values using 'UPDATE' to indicate type of action
     'SET' tags to set a new value for a column

 # Example using UPDATE
UPDATE users SET age = '95' WHERE userId = 1223;

  1. changes 'user' with 'userId' 12223 with its correct age which is set to 95. 

# DELETE 

  1. Almost sam as UPDATE code wise and simply use 'DELTE FROM ' to indicate
     frow where you are

# Example using DELETE
DELETE FROM users WHERE userID 10

  1. deletes users user its userId id 10. 

# UPSERT or INSERT ON CONFLICT

  1. Basically checks if query matches and updates a matach query or creates a
     new row if no match on existing values
