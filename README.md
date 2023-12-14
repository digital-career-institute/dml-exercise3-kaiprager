# DML exercise3
Exercise Set:
Exercise Set:
create student table , add columns such as maths,chemistry,physics, and age.

add entries of studnets who have scored more than 75 in physics.add entry for the studnet whose name is alice and bob.

add some students who scored less than 70.

mysql> CREATE TABLE students (
    ->     studentID INT PRIMARY KEY AUTO_INCREMENT,
    ->     name VARCHAR(100),
    ->     maths INT,
    ->     chemistry INT,
    ->     physics INT,
    ->     age INT
    -> );
Query OK, 0 rows affected (0,02 sec)

mysql> INSERT INTO students (name, maths, chemistry, physics, age)
    -> VALUES
    ->     ('Alice', 80, 85, 80, 20),
    ->     ('Bob', 78, 79, 76, 21);
Query OK, 2 rows affected (0,01 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> INSERT INTO students (name, maths, chemistry, physics, age)
    -> VALUES
    ->     ('Charlie', 65, 68, 72, 22),
    ->     ('Daisy', 70, 67, 68, 19),
    ->     ('Ethan', 62, 65, 69, 20);
Query OK, 3 rows affected (0,01 sec)
Records: 3  Duplicates: 0  Warnings: 0


Task 1: SELECT Queries

1.Retrieve all information from the "Students" table:

mysql> SELECT *
    -> FROM students;
+-----------+---------+-------+-----------+---------+------+
| studentID | name    | maths | chemistry | physics | age  |
+-----------+---------+-------+-----------+---------+------+
|         1 | Alice   |    80 |        85 |      80 |   20 |
|         2 | Bob     |    78 |        79 |      76 |   21 |
|         3 | Charlie |    65 |        68 |      72 |   22 |
|         4 | Daisy   |    70 |        67 |      68 |   19 |
|         5 | Ethan   |    62 |        65 |      69 |   20 |
+-----------+---------+-------+-----------+---------+------+
5 rows in set (0,00 sec)


2.Fetch only the names and ages of students:

mysql> SELECT name, age
    -> FROM students;
+---------+------+
| name    | age  |
+---------+------+
| Alice   |   20 |
| Bob     |   21 |
| Charlie |   22 |
| Daisy   |   19 |
| Ethan   |   20 |
+---------+------+
5 rows in set (0,00 sec)


3.Get the details of students who scored above 75 in the "Physics" subject:

mysql> SELECT *
    -> FROM students
    -> WHERE physics > 75;
+-----------+-------+-------+-----------+---------+------+
| studentID | name  | maths | chemistry | physics | age  |
+-----------+-------+-------+-----------+---------+------+
|         1 | Alice |    80 |        85 |      80 |   20 |
|         2 | Bob   |    78 |        79 |      76 |   21 |
+-----------+-------+-------+-----------+---------+------+
2 rows in set (0,00 sec)


4.Insert a new student into the "Students" table:

mysql> INSERT INTO students (name, maths, chemistry, physics, age)
    -> VALUES(
    -> 'Vanessa', 58, 82, 67, 24
    -> );
Query OK, 1 row affected (0,01 sec)


5.Add a student who excelled only in Mathematics and Chemistry:

mysql> INSERT INTO students (name, maths, chemistry, physics, age)
    -> VALUES(
    -> 'Dirk', 92, 95, 12, 21
    -> );
Query OK, 1 row affected (0,01 sec)


6.Update the age of a student named "Alice" to 23 years:

mysql> UPDATE students
    -> SET age = 23
    -> WHERE name = 'Alice';
Query OK, 1 row affected (0,01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

7.Increase the Chemistry score of all students by 5 points:

8.Delete a student named "Bob" from the "Students" table:

mysql> UPDATE students
    -> SET chemistry = chemistry + 5;
Query OK, 7 rows affected (0,01 sec)
Rows matched: 7  Changed: 7  Warnings: 0


9.Remove all students who scored below 70 in Mathematics:

mysql> DELETE FROM students
    -> WHERE maths < 70;
Query OK, 3 rows affected (0,01 sec)

