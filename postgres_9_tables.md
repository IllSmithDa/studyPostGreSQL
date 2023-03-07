# Creating Tables syntax

  1. You can create tables using 'CREATE TABLE' key phrase followed by table
     name
  
    e.g
    CREATE TABLE accounts (
    	user_id serial PRIMARY KEY,
    	username VARCHAR ( 50 ) UNIQUE NOT NULL,
    	password VARCHAR ( 50 ) NOT NULL,
    	email VARCHAR ( 255 ) UNIQUE NOT NULL,
    	created_on TIMESTAMP NOT NULL,
            last_login TIMESTAMP 
    );

      a. NOT NULL means this field cannot be empty or NULL