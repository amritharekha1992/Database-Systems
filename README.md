# Database-Systems
Database Systems Repository

# Problem #1 – For each of our tables, retrieve all rows and all columns.Tables are Student, Faculty, Offering, Course, and Enrollment
# (no need to sort at this point)
Answer:
SELECT * FROM Student S;
SELECT * FROM Faculty F;
SELECT * FROM Offering O;
SELECT * FROM Course C;
SELECT * FROM Enrollment E;

# Problem #2 – Retrieve the student number, student first name, and student last name for all students
# Sort the results by student last name then by student first name Use the ASC keyword on the query
Answer:
SELECT S.STDNO, S.STDFIRSTNAME, S.STDLASTNAME FROM Student S
ORDER BY S.STDLASTNAME ASC, S.STDFIRSTNAME ASC;
# Repeat the query omitting ASC
Answer:
SELECT S.STDNO,S.STDFIRSTNAME,S.STDLASTNAME FROM Student S
ORDER BY S.STDLASTNAME, S.STDFIRSTNAME;

# Problem #3 – Retrieve the student last name, student first name, and GPA for all students
# Sort the results by GPA highest first, then by student last name, then by student first name Use column names to sort (omit ASC)
Answer:
SELECT S.STDLASTNAME, S.STDFIRSTNAME, S.STDGPA FROM Student S
ORDER BY S.STDGPA DESC, S.STDLASTNAME, S.STDFIRSTNAME;
# Repeat the query using positional notation 
Answer:
SELECT S.STDLASTNAME, S.STDFIRSTNAME, S.STDGPA FROM Student S
ORDER BY 3 DESC, 1, 2;

# Problem #4 – Retrieve the student city and class for all students with duplicates Repeat query without duplicates
Answer:
SELECT S.STDCITY, S.STDCLASS FROM Student S;
# Repeat query without duplicates
Answer:
SELECT DISTINCT S.STDCITY, S.STDCLASS FROM Student S;

# Problem #5 – Retrieve the student last name, student first name, and GPA for all students with a GPA greater than 3.2
Answer:
SELECT S.STDLASTNAME, S.STDFIRSTNAME, S.STDGPA FROM Student S WHERE S.STDGPA > 3.2

# Problem #6 – Retrieve the student last name, student first name, and GPA for all students with a GPA (more than 2.2 and less than 2.7) OR (more than 3.2 and less than 3.8)
Answer:
SELECT S.STDLASTNAME, S.STDFIRSTNAME, S.STDGPA
FROM Student S
WHERE ((S.STDGPA > 2.2 AND S.STDGPA < 2.7) OR (S.STDGPA > 3.2 AND S.STDGPA < 3.8));

# Problem #7 – Retrieve the student last name, student first name, and GPA for all students with a GPA that is between 2.7 and 3.2 inclusive
Answer:
SELECT S.STDLASTNAME, S.STDFIRSTNAME, S.STDGPA
FROM Student S
WHERE S.STDGPA BETWEEN 2.7 AND 3.2;

# Problem #8 – Retrieve the offer number, course number, year, and faculty number from all course offerings that has not yet been assigned a Faculty
Answer:
SELECT O.OFFERNO, O.COURSENO, O.OFFYEAR, O.FACNO
FROM Offering O
WHERE O.FACNO IS NULL;
# Repeat query for course offerings that have been assigned a Faculty
Answer:
SELECT O.OFFERNO, O.COURSENO, O.OFFYEAR, O. FACNO
FROM Offering O
WHERE O.FACNO IS NOT NULL;
