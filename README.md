# DATABASE-BACKUP-AND-RECOVERY-TASK-3



CREATE DATABASE schooldb;
USE schooldb;

CREATE TABLE students (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    age INT
);

INSERT INTO students (name, age) VALUES
('Alice', 20),
('Bob', 22),
('Charlie', 21);


|id |name    |age |
|---|--------|-----|
| 1 | Kishor | 20.  |
| 2 | Sobha  | 22.  |
| 3 |Badri   | 21.  |

2
SELECT * FROM students
INTO OUTFILE '/tmp/students.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n';






3
CREATE DATABASE schooldb;
\c schooldb;

CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    age INT
);






4
\COPY students(id, name, age) FROM '/tmp/students.csv' DELIMITER ',' CSV;


















