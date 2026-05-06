practical no:1
Problem Statement 
The aim of this project is to design a University Management System Database that can 
manage information about students, instructors, courses, and enrollments. The system 
must 
maintain the relationships between these entities: 
● Students can enroll in multiple courses. 
● Courses can have multiple students. 
● Instructors can teach one or more courses.

Step 1: Create the database 
CREATE DATABASE UniversityDB;  
USE UniversityDB;

Step 2: Create Tables 
1. Student Table  
CREATE TABLE Student ( 
StudentID INT PRIMARY KEY AUTO_INCREMENT, 
Name VARCHAR(100) NOT NULL, 
Email VARCHAR(100) UNIQUE NOT NULL, 
Age INT CHECK (Age > 0), 
Address VARCHAR(255) 
);

2.Instructor TABLE 
CREATE TABLE Instructor ( 
InstructorID INT PRIMARY KEY AUTO_INCREMENT, 
Name VARCHAR(100) NOT NULL, 
Email VARCHAR(100) UNIQUE NOT NULL, 
Department VARCHAR(100) 
); 

3.Course Table 
CREATE TABLE Course ( 
CourseID INT PRIMARY KEY AUTO_INCREMENT, 
CourseName VARCHAR(100) NOT NULL, 
Credits INT CHECK (Credits &gt; 0), 
InstructorID INT, 
FOREIGN KEY (InstructorID) REFERENCES Instructor(InstructorID) 
ON DELETE SET NULL 
ON UPDATE CASCADE); 

4.Enrollment Table 
CREATE TABLE Enrollment ( 
EnrollmentID INT PRIMARY KEY AUTO_INCREMENT, 
StudentID INT, 
CourseID INT, 
EnrollmentDate DATE NOT NULL, 
FOREIGN KEY (StudentID) REFERENCES Student(StudentID) 
ON DELETE CASCADE 
ON UPDATE CASCADE, 
FOREIGN KEY (CourseID) REFERENCES Course(CourseID) 
ON DELETE CASCADE 
ON UPDATE CASCADE 

Step 4: Sample Data Insertion -- Instructors  
INSERT INTO Instructor(Name,Email,Department)VALUES        
('dr.smith','smith@university.com','Computer Science'),  
('Dr.Johnson','Johnson@univerity.com','Mathematics'); 

--student 
INSERT INTO Student(Name,Email,Age,Address)VALUES 
('Alice','alice@example.com',20,'123 MainSt'), 
('Bob','bob@example.com',22,'456 Oak St');

--course 
INSERT INTO Course(CourseName,Credits,InstructorID) VALUES 
('Database Systems',3,1),('Calculus',4,2); 

--Enrollment 
INSERT INTO Enrollment(StudentID,CourseID,EnrollmentDate)VALUES 
(1,1,'2026-01-31'),(1,2,'2026-01-31'),(2,2,'2026-01-31');

Step 5: Verify Relationships -- List all students with their courses 
SELECT s.Name AS Student, c.CourseName, e.EnrollmentDate 
FROM Enrollment e 
JOIN Student s ON e.StudentID = s.StudentID 
JOIN Course c ON e.CourseID = c.CourseID; 

-- List all courses with their instructors 
SELECT c.CourseName, i.Name AS Instructor 
FROM Course c 
JOIN Instructor i ON c.InstructorID = i.InstructorID;






















