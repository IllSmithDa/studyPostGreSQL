# Setup 

  1. Install Postgre SQL from the link or just google it

    a. https://www.enterprisedb.com/downloads/postgres-postgresql-downloads

  2. Open the psql terminal in the app folder (also known as SQL Shell) and
     enter the required password and leave everything else blank

# Setup server for localhost and Pg Admin

  1. click 'create server' under Server 

  2. must have include a server name which is whatever you want to name server
     and the second is the host name which is 'localhost' for local use
     
  3. enter database name on creation in the 'Maintenance Database' section as
     well as a username and password for data base as well


# What is a relational Data base? 

  1. Relational databse is when two or more tables have some kind of relationship between then

  2. PostGreSQL is open source and is free compared to Oracle. 


# Creating Tables syntax

  1. You can create tables using 'CREATE TABLE' key phrase followed by table
     name
  
# Exmple One
CREATE TABLE accounts (
	user_id serial PRIMARY KEY,
	username VARCHAR ( 50 ) UNIQUE NOT NULL,
	password VARCHAR ( 50 ) NOT NULL,
	email VARCHAR ( 255 ) UNIQUE NOT NULL,
	created_on TIMESTAMP NOT NULL,
        last_login TIMESTAMP 
);

  1. NOT NULL means this field cannot be empty or NULL