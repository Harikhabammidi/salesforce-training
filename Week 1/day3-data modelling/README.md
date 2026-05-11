# College Management System using Salesforce Concepts

##  Understanding Salesforce Basics

### Difference Between App, Object, Record, and Field

| Term | Description | Example |
|------|-------------|---------|
| App | A group of related tools and objects created for a particular process | College Management Application |
| Object | A storage structure similar to a database table | Student, Faculty, Course |
| Record | One individual row of data inside an object | Details of one student |
| Field | A specific attribute stored in a record | Name, Email, Department |

---

# Standard Objects vs Custom Objects

| Standard Objects | Custom Objects |
|------------------|----------------|
| Provided by Salesforce by default | Created according to organization needs |
| Used for common CRM activities | Used for unique business requirements |
| Examples: Account, Contact, Opportunity | Examples: Student, Faculty, Department |
| Available automatically in the platform | Designed manually by developers/admins |
| Mostly fixed structure | Can be customized easily |

---

# College Management Data Structure

## Student Object

Used to maintain student-related information.

### Fields

- Student ID
- Student Name
- Email
- Mobile Number
- Department
- Course Name

---

## Faculty Object

Used to store faculty details.

### Fields

- Faculty ID
- Faculty Name
- Email
- Department
- Subject Expertise

---

## Course Object

Contains information about available courses.

### Fields

- Course ID
- Course Title
- Seat Capacity
- Seats Available
- Assigned Faculty
- Department

---

## Department Object

Maintains department information.

### Fields

- Department ID
- Department Name
- Head of Department

---

#  Relationships Between Objects

| Parent | Child | Relationship |
|--------|-------|--------------|
| Department | Student | One-to-Many |
| Department | Faculty | One-to-Many |
| Department | Course | One-to-Many |
| Faculty | Course | One-to-Many |
| Course | Student | One-to-Many |

---

# Data Model Diagram

                           +---------------------------+
                           |        Department         |
                           +---------------------------+
                           | Dept ID                   |
                           | Dept Name                 |
                           | Head of Department        |
                           +---------------------------+
                              /           |           \
                             /            |            \
                            /             |             \
                           /              |              \
                          v               v               v

               +----------------+   +----------------+   +----------------+
               |    Student     |   |    Faculty     |   |     Course     |
               +----------------+   +----------------+   +----------------+
               | Student ID     |   | Faculty ID     |   | Course ID      |
               | Student Name   |   | Faculty Name   |   | Course Name    |
               | Email          |   | Email          |   | Seat Capacity  |
               | Mobile Number  |   | Expertise      |   | Seats Left     |
               | Semester       |   | Experience     |   | Credits        |
               +----------------+   +----------------+   +----------------+
                        \                    |                    /
                         \                   |                   /
                          \                  |                  /
                           \                 |                 /
                            \                |                /
                             \               |               /
                              \              |              /
                               +--------------------------+
                               |      Enrollment Hub      |
                               +--------------------------+
                               | Enrollment ID            |
                               | Student ID               |
                               | Course ID                |
                               | Enrollment Date          |
                               | Status                   |
                               +--------------------------+


Relationships:

1 Department  → Many Students  
1 Department  → Many Faculty Members  
1 Department  → Many Courses  
1 Faculty     → Many Courses  
1 Student     → Many Enrollments  
1 Course      → Many Enrollments

Formula Fields
Student Full Name
Formula
First Name + " " + Last Name
Purpose

Automatically joins first name and last name into a single value for consistency.

Seats Remaining
Formula
Total Seats - Enrolled Students
Purpose

Displays the number of seats left in a course automatically.

Student Percentage
Formula
(Scored Marks / Total Marks) * 100
Purpose

Calculates percentage accurately without manual calculation.

✅ Validation Rules
Mandatory Email Validation
Rule

Email should not be left blank.

Purpose

Ensures proper communication and complete records.

Valid Student Age
Rule

Age value must be greater than zero.

Purpose

Avoids incorrect or invalid student data.

Seat Limit Validation
Rule

Number of enrolled students cannot exceed total seats.

Purpose

Prevents course over-allocation and maintains proper seat management.

Importance of Structured Enterprise Data

Structured data helps organizations organize and manage information efficiently. Instead of maintaining disconnected spreadsheets, enterprise systems use connected data models for better performance and accuracy.

Benefits in a College Management System
Easy management of student and faculty records
Better connection between departments and courses
Faster report generation
Reduced duplicate data
Improved data consistency
Supports automation and future analytics

Using structured relationships between objects makes data retrieval easier and improves overall system management.
