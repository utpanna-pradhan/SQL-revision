## ✅ Table Creation & Basic Manipulation 
# 1.Create a table named 'students'.
- CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    department VARCHAR(50)
  );

# 2.Insert 5 records into 'students'.
- INSERT INTO students VALUES
(1, 'Alice', 20, 'CS'),
(2, 'Bob', 22, 'IT'),
(3, 'Charlie', 21, 'CS'),
(4, 'David', 23, 'ECE'),
(5, 'Eve', 22, 'IT');

# 3.Fetch all student records.
- SELECT * FROM students;
  
# 4.Fetch names of students from IT.
- SELECT name FROM students WHERE department = 'IT';

# 5.Update age of student with id 2.
- UPDATE students SET age = 23 WHERE id = 2;

# 6.Delete student named Charlie.
- DELETE FROM students WHERE name = 'Charlie';

# 7.Add column 'email'.
- ALTER TABLE students ADD COLUMN email VARCHAR(100);

# 8.Set email for Alice.
- UPDATE students SET email = 'alice@example.com' WHERE name = 'Alice';

# 9.Create a table 'courses'.
    CREATE TABLE courses (
      course_id INT PRIMARY KEY,
      course_name VARCHAR(100)
    );
    
# 10.Insert data into 'courses'.
INSERT INTO courses VALUES
(1, 'SQL'), (2, 'Python'), (3, 'React');

# 11.Create table 'enrollments'.
CREATE TABLE enrollments (
  student_id INT,
  course_id INT,
  FOREIGN KEY (student_id) REFERENCES students(id),
  FOREIGN KEY (course_id) REFERENCES courses(course_id)
);

# 12.Insert enrollment records.
INSERT INTO enrollments VALUES
(1, 1), (1, 2), (2, 1), (4, 3);

# 13.Get all students with their courses.
SELECT s.name, c.course_name
FROM students s
JOIN enrollments e ON s.id = e.student_id
JOIN courses c ON e.course_id = c.course_id;

# 14.Count students in each department.
SELECT department, COUNT(*) FROM students GROUP BY department;

# 15.List students not enrolled in any course.
SELECT * FROM students
WHERE id NOT IN (SELECT student_id FROM enrollments);

# 16.Create view for students older than 21.
CREATE VIEW view_students_21 AS
SELECT * FROM students WHERE age > 21;

# 17.Display view data.
SELECT * FROM view_students_21;

# 18.Drop the view.
DROP VIEW view_students_21;

# 19.Get student with max age.
SELECT * FROM students
WHERE age = (SELECT MAX(age) FROM students);

# 20.Rename 'department' to 'dept'.
ALTER TABLE students RENAME COLUMN department TO dept;

# 21.Fetch course name and count of enrolled students.
SELECT c.course_name, COUNT(e.student_id) AS total
FROM courses c
LEFT JOIN enrollments e ON c.course_id = e.course_id
GROUP BY c.course_name;

# 22.Inner join between students and enrollments.
SELECT s.name, e.course_id
FROM students s
JOIN enrollments e ON s.id = e.student_id;

# 23.Right join students and enrollments.
SELECT s.name, c.course_name
FROM students s
RIGHT JOIN enrollments e ON s.id = e.student_id
JOIN courses c ON e.course_id = c.course_id;

# 24.Left join students and courses.
SELECT s.name, c.course_name
FROM students s
LEFT JOIN enrollments e ON s.id = e.student_id
LEFT JOIN courses c ON e.course_id = c.course_id;

# 25.Full outer join workaround (MySQL doesn’t support directly).
SELECT s.name, c.course_name
FROM students s
LEFT JOIN enrollments e ON s.id = e.student_id
LEFT JOIN courses c ON e.course_id = c.course_id
UNION
SELECT s.name, c.course_name
FROM students s
RIGHT JOIN enrollments e ON s.id = e.student_id
RIGHT JOIN courses c ON e.course_id = c.course_id;

# 26.Find duplicate student names.
SELECT name, COUNT(*) 
FROM students 
GROUP BY name 
HAVING COUNT(*) > 1;

# 27.Get youngest student.
SELECT * FROM students
ORDER BY age ASC LIMIT 1;

# 28.Get students whose names end with 'e'.
SELECT * FROM students WHERE name LIKE '%e';

# 29.Count how many courses each student enrolled in.
SELECT s.name, COUNT(e.course_id) AS course_count
FROM students s
JOIN enrollments e ON s.id = e.student_id
GROUP BY s.name;

# 30.Find students who have taken both course 1 and 2.
SELECT student_id
FROM enrollments
WHERE course_id IN (1, 2)
GROUP BY student_id
HAVING COUNT(DISTINCT course_id) = 2;


# 31.Get students enrolled in SQL but not in Python.
SELECT student_id FROM enrollments WHERE course_id = 1
EXCEPT
SELECT student_id FROM enrollments WHERE course_id = 2;

# 32.Find avg age of IT students.
SELECT AVG(age) FROM students WHERE department = 'IT';

# 33.Display students in alphabetical order.
SELECT * FROM students ORDER BY name;

# 34.Show departments in uppercase.
SELECT UPPER(department) FROM students;

# 35.Concatenate name and department.
SELECT CONCAT(name, ' - ', department) AS info FROM students;

# 36.Display email in lowercase.
SELECT LOWER(email) FROM students;

# 37.Show current date.
SELECT CURRENT_DATE;

# 38.Round age/3 to 2 decimal places.
SELECT ROUND(age/3.0, 2) FROM students;

# 39.Count total enrolled records.
SELECT COUNT(*) FROM enrollments;

# 40.Count unique students in enrollments.
SELECT COUNT(DISTINCT student_id) FROM enrollments;


# 41.Create backup of students table.
CREATE TABLE students_backup AS SELECT * FROM students;

# 42.Delete all records from enrollments (keep table).
DELETE FROM enrollments;

# 43.Truncate enrollments (reset auto ID, fast delete).
TRUNCATE TABLE enrollments;

# 44.Drop table courses.
DROP TABLE courses;

# 45.Create user 'devuser'.
CREATE USER 'devuser' IDENTIFIED BY 'password';

# 46.Grant SELECT on students to devuser.
GRANT SELECT ON students TO devuser;

# 47.Revoke SELECT from devuser.
REVOKE SELECT ON students FROM devuser;

# 48.Start transaction.
START TRANSACTION;

# 49.Commit transaction.
COMMIT;

# 50.Rollback transaction.
ROLLBACK;

# 51.Assign row numbers to students.

sql
Copy
Edit
SELECT name, ROW_NUMBER() OVER (ORDER BY name) AS row_num FROM students;
# 52.Rank students by age.

sql
Copy
Edit
SELECT name, age, RANK() OVER (ORDER BY age DESC) AS age_rank FROM students;
# 53.Find lead/lag of student ages.

sql
Copy
Edit
SELECT name, age, 
  LAG(age) OVER (ORDER BY id) AS prev_age,
  LEAD(age) OVER (ORDER BY id) AS next_age
FROM students;
# 54.Partition count by department.

sql
Copy
Edit
SELECT name, department,
COUNT(*) OVER (PARTITION BY department) AS dept_count
FROM students;
# 55.Check if student has more than one enrollment.

sql
Copy
Edit
SELECT student_id, COUNT(*) FROM enrollments
GROUP BY student_id
HAVING COUNT(*) > 1;
Find students enrolled in maximum courses.

sql
Copy
Edit
SELECT student_id FROM enrollments
GROUP BY student_id
HAVING COUNT(course_id) = (
  SELECT MAX(course_count)
  FROM (
    SELECT COUNT(course_id) AS course_count
    FROM enrollments
    GROUP BY student_id
  ) AS sub
);
Find course(s) with zero enrollments.

sql
Copy
Edit
SELECT * FROM courses
WHERE course_id NOT IN (SELECT DISTINCT course_id FROM enrollments);
Count characters in student names.

sql
Copy
Edit
SELECT name, LENGTH(name) FROM students;
Show current timestamp.

sql
Copy
Edit
SELECT CURRENT_TIMESTAMP;
Get student name in reverse.

sql
Copy
Edit
SELECT REVERSE(name) FROM students;
Extract first 3 letters of each name.

sql
Copy
Edit
SELECT SUBSTRING(name, 1, 3) FROM students;
Replace 'a' with '@' in names.

sql
Copy
Edit
SELECT REPLACE(name, 'a', '@') FROM students;
Create temporary table.

sql
Copy
Edit
CREATE TEMPORARY TABLE temp_ids (id INT);
Insert into temporary table.

sql
Copy
Edit
INSERT INTO temp_ids VALUES (101), (102);
List even-aged students.

sql
Copy
Edit
SELECT * FROM students WHERE MOD(age, 2) = 0;
Check students born in February (assuming birthdate).

sql
Copy
Edit
-- Assuming column birthdate exists
SELECT * FROM students WHERE MONTH(birthdate) = 2;
Add constraint to make email unique.

sql
Copy
Edit
ALTER TABLE students ADD CONSTRAINT unique_email UNIQUE(email);
Drop 'email' column.

sql
Copy
Edit
ALTER TABLE students DROP COLUMN email;
Get top 2 youngest students.

sql
Copy
Edit
SELECT * FROM students ORDER BY age ASC LIMIT 2;
Get number of students in each course.

sql
Copy
Edit
SELECT course_id, COUNT(student_id)
FROM enrollments
GROUP BY course_id;
Replace NULLs in email with 'N/A'.

sql
Copy
Edit
SELECT COALESCE(email, 'N/A') FROM students;
Use CASE to label students.

sql
Copy
Edit
SELECT name, age,
CASE 
  WHEN age < 21 THEN 'Teen'
  WHEN age BETWEEN 21 AND 23 THEN 'Young Adult'
  ELSE 'Adult'
END AS age_group
FROM students;
Find common student IDs between two tables.

sql
Copy
Edit
SELECT id FROM students
INTERSECT
SELECT student_id FROM enrollments;
Find symmetric difference of student-course combos.

sql
Copy
Edit
SELECT student_id, course_id FROM enrollments
UNION
SELECT student_id, course_id FROM enrollments
EXCEPT
SELECT student_id, course_id FROM enrollments;
Calculate total and average age of students.

sql
Copy
Edit
SELECT SUM(age), AVG(age) FROM students;
Get students with palindrome names.

sql
Copy
Edit
SELECT * FROM students
WHERE name = REVERSE(name);
Check if course name has 'SQL'.

sql
Copy
Edit
SELECT * FROM courses WHERE course_name LIKE '%SQL%';
Find students with NULL emails.

sql
Copy
Edit
SELECT * FROM students WHERE email IS NULL;
Find students with non-NULL emails.

sql
Copy
Edit
SELECT * FROM students WHERE email IS NOT NULL;
List all columns in students table.

sql
Copy
Edit
SELECT COLUMN_NAME
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'students';
