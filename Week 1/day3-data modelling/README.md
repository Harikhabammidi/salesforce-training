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

# Formula Fields

## 1. Student Full Name

### Formula

```text
First Name + " " + Last Name
```

### Purpose

Automatically combines the student's first name and last name into a single full name field for better consistency and readability.

---

## 2. Seats Remaining

### Formula

```text
Total Seats - Enrolled Students
```

### Purpose

Calculates the number of available seats left in a course automatically and helps avoid overbooking.

---

## 3. Student Percentage

### Formula

```text
(Scored Marks / Total Marks) * 100
```

### Purpose

Automatically computes the percentage obtained by a student and reduces manual calculation errors.

---

# Validation Rules

## 1. Mandatory Email Validation

### Rule

The Email field cannot be empty.

### Purpose

Ensures every student or faculty record contains proper contact information for communication.

---

## 2. Valid Student Age

### Rule

Student age must be greater than zero.

### Purpose

Prevents invalid or incorrect age entries from being stored in the system.

---

## 3. Seat Limit Validation

### Rule

Enrolled student count should not exceed the total seat capacity.

### Purpose

Helps maintain proper admission limits and prevents excess enrollments.

---

# Importance of Structured Enterprise Data

Structured enterprise data allows organizations to manage information in an organized and connected format. Instead of using scattered spreadsheets, systems with structured data improve efficiency, accuracy, and scalability.

## Benefits in a College Management System

- Simplifies student and faculty management
- Maintains clear relationships between departments and courses
- Enables faster report generation
- Reduces duplicate or inconsistent data
- Improves overall data accuracy
- Supports automation and analytical processes

Structured object relationships make it easier to retrieve information, manage records efficiently, and improve decision-making across the organization.
