# Repo_setup_basicquery
I created a SQL script that sets up a training database, inserts sample data, and demonstrates basic data retrieval to understand SQL syntax and execution flow.”
-- 
-- Purpose  : SQL basics for intern training
-- Outcome  : Understand database, table,
--  insert, and select operations

CREATE DATABASE intern_training_db;
USE intern_training_db;

CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    age INT
);

INSERT INTO students (id, name, email, age) VALUES
(1, 'rahul boyer', 'rahul.boyer@gmail.com', 20),
(2, 'oriya pexy', 'oriya.pexy@gmail.com', 21),
(3, 'nAmit Patel', 'namit.patel@gmail.com', 19),
(4, 'kneha nexi', 'kneha.nexi@gmail.com', 22),
(5, 'mohan zexy', 'mohan.zexy@gmail.com', 20);


SELECT * FROM students;
SELECT name, email FROM students;
SELECT name, age FROM students;
SELECT * FROM students
WHERE age > 20;
SELECT name, email FROM students
WHERE id = 3;
SELECT * FROM students;

-- Age equals 20
SELECT * FROM students
WHERE age = 20;

-- Age between 20 and 22
SELECT * FROM students
WHERE age BETWEEN 20 AND 22;
------------------##------------------------IN ADVANCE------------------------------------------
-- Name starts with 'R'
SELECT * FROM students
WHERE name LIKE 'R%';

-- Gmail users only
SELECT name, email
FROM students
WHERE email LIKE '%@gmail.com';

-- Multiple conditions using AND
SELECT * FROM students
WHERE age > 19 AND age < 22;

-- Using OR condition
SELECT * FROM students
WHERE age = 19 OR age = 22;

-- Exclude age 20
SELECT * FROM students
WHERE age <> 20;

-- Order results
SELECT name, age
FROM students
ORDER BY age DESC;

-- Limit output
SELECT * FROM students
LIMIT 3;
