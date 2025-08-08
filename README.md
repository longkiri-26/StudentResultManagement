# Student Result Management System

Overview

The Student Result Management System is a Java-based application designed to manage student records and their academic results. It provides functionalities for both students and administrators, including viewing results, adding new students, inserting results, and managing student data.

Features
Student Features
View Results: Students can view their academic results by entering their roll number.

User-Friendly Interface: Simple and intuitive interface for easy navigation.

Admin Features
Add New Students: Administrators can add new student records to the system.

Insert Results: Admins can input and update student results for various subjects.

View Registered Students: Display a list of all registered students.

View All Results: Access and manage all student results in one place.

Secure Login: Admin access is protected with a username and password.

Technologies Used
Programming Language: Java

Database: MySQL

Libraries:

JDBC for database connectivity

Swing for GUI components

JUnit for testing (included but not fully implemented)

Database Schema
The system uses a MySQL database named srm with the following tables:

student: Stores student details (roll number, name, course, branch, gender, father's name).

result: Stores academic results (roll number, subject marks, total marks, pass/fail status).

Setup Instructions
Prerequisites
Java Development Kit (JDK) 8 or later

MySQL Server

MySQL Connector/J (JDBC driver for MySQL)

Installation Steps
Clone the Repository:

bash
git clone https://github.com/yourusername/student-result-management-system.git
cd student-result-management-system
Database Setup:

Create a MySQL database named srm.

Execute the following SQL commands to create the required tables:

sql
CREATE TABLE student (
    rollNo VARCHAR(20) PRIMARY KEY,
    course VARCHAR(50),
    branch VARCHAR(50),
    name VARCHAR(100),
    gender VARCHAR(10),
    fatherName VARCHAR(100)
);

CREATE TABLE result (
    rollNo VARCHAR(20) PRIMARY KEY,
    OS VARCHAR(10),
    AAD VARCHAR(10),
    CN VARCHAR(10),
    CD VARCHAR(10),
    DBMS VARCHAR(10),
    FOREIGN KEY (rollNo) REFERENCES student(rollNo)
);
Configure Database Connection:

Update the database connection details in each Java file where DriverManager.getConnection is called. Replace "username" and "password" with your MySQL username and password.

java
Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/srm", "your_username", "your_password");
Run the Application:

Compile and run the index.java file to start the application.

bash
javac index.java
java index
Usage
Student Login:

Click the "Student" button on the main screen.

Enter your roll number to view your results.

Admin Login:

Click the "Admin" button on the main screen.

Enter the username (admin) and password (pass) to access the admin dashboard.

Use the admin dashboard to add students, insert results, or view registered students and results.
