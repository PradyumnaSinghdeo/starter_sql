```sql


CREATE DATABASE startersql;

USE startersql;

CREATE TABLE users (
id INT AUTO_INCREMENT PRIMARY KEY,
 name VARCHAR(100) NOT NULL,
 email VARCHAR(100) UNIQUE NOT NULL,
 gender ENUM('Male', 'Female', 'Other'),
 date_of_birth DATE,
 created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

DROP DATABASE startersql;

SELECT * FROM users;

SELECT name, email FROM users;

RENAME TABLE users TO customers;

RENAME TABLE customers TO users;

-- ALTER TABLE METHOD  (You can use ALTER TABLE to modify an existing table.)

ALTER TABLE users ADD COLUMN is_active BOOLEAN DEFAULT TRUE;

ALTER TABLE users DROP COLUMN is_active;

ALTER TABLE users MODIFY COLUMN name VARCHAR(150);

-- Move a Column to the First Position

ALTER TABLE users MODIFY COLUMN email VARCHAR(100) FIRST;

ALTER TABLE users MODIFY COLUMN gender ENUM('Male', 'Female', 'Other') AFTER name;

-- Inserting Data into MySQL Tables

INSERT INTO users VALUES
(1, 'Alice', 'alice@example.com', 'Female', '1995-05-14', DEFAULT);

INSERT INTO users (name, email, gender, date_of_birth) VALUES
('Bob', 'bob@example.com', 'Male', '1990-11-23');

INSERT INTO users (name, email, gender, date_of_birth) VALUES
('Bob', 'bob@example.com', 'Male', '1990-11-23'),
('Charlie', 'charlie@example.com', 'Other', '1988-02-17');

INSERT INTO users (name, email, gender, date_of_birth) VALUES
('Charlie', 'charlie@example.com', 'Other', '1988-02-17'),
('David', 'david@example.com', 'Male', '2000-08-09'),
('Eva', 'eva@example.com', 'Female', '1993-12-30');

-- Querying Data in MySQL using SELECT

SELECT * FROM users;

SELECT * FROM users WHERE gender = 'Male';

SELECT * FROM users WHERE gender != 'Female';
-- or
SELECT * FROM users WHERE gender <> 'Female';

SELECT * FROM users WHERE date_of_birth < '1995-01-01';
SELECT * FROM users WHERE id > 10;

SELECT * FROM users WHERE id >= 5;
SELECT * FROM users WHERE id <= 20;

-- Working with NULL


