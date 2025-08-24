# DATABASE-BACKUP-AND-RECOVERY-TASK-3

  DATABASE MIGRATION SUMMERY REPORT

  INTERNSHIP TASK: Task-3(Database Migration)
  INTERN:[Bokkisam Priyankisho Reddy]
  COMPANY:CODTECH IT Solutions
  DATE:[23-08-2025]



 CREATING AND USING DATABASE :
 
CREATE DATABASE schooldb;
USE schooldb;

STEP 1: CREATING TABLE IN MySQL(source):

QUERY:

CREATE TABLE students (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    age INT
);

INSERT INTO students (name, age) VALUES
('Alice', 20),
('Bob', 22),
('Charlie', 21);


|id |name    |age  |
|---|--------|-----|
| 1 | Kishor | 20  |
| 2 | Sobha  | 22  |
| 3 | Badri  | 21  |

STEP 2: EXPORTING DATA FROM MYSQL (CSV file ):

QUERY:

SELECT * FROM students
INTO OUTFILE '/tmp/students.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n';

| id  | name  | age |
|-----|-------|-----|
| 1   | Kishor| 20  |
| 2   | Sobha | 22  |
| 3   | Badri | 21  |

STEP 3: CREATE TABLE IN POSTGRESQL(EMPTY TARGET TABLE)

CREATING DATABASE AND TABLE FOR STEP 3 PROCESS:

QUERY:

CREATE DATABASE schooldb;
\c schooldb;

CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

| id | name | age|
|----|------|----|
|    |      |    |

STEP 4 : IMPORT DATA INTO POSTGRESQL(USING\COPY)

QUERY:

\COPY students(id, name, age) FROM '/tmp/students.csv' DELIMITER ',' CSV;

| id | name   | age  |
|----|--------|------|
| 1  | Kishor | 20   |
| 2  | Sobha  | 22   |
| 3  | Badri  | 21   |


FINAL CHECK :

QUERY:

SELECT * FROM students;

| id  | name   | age |
|-----|--------|-----|
| 1   | Kishor | 20  |
| 2   | Sobha  | 22  |
| 3   | Badri  | 21  |

(3 rows)














