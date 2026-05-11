# 🎓 College Management System using Salesforce Concepts

## 📌 Understanding Salesforce Basics

### Difference Between App, Object, Record, and Field

| Term | Description | Example |
|------|-------------|---------|
| App | A group of related tools and objects created for a particular process | College Management Application |
| Object | A storage structure similar to a database table | Student, Faculty, Course |
| Record | One individual row of data inside an object | Details of one student |
| Field | A specific attribute stored in a record | Name, Email, Department |

---

# 📚 Standard Objects vs Custom Objects

| Standard Objects | Custom Objects |
|------------------|----------------|
| Provided by Salesforce by default | Created according to organization needs |
| Used for common CRM activities | Used for unique business requirements |
| Examples: Account, Contact, Opportunity | Examples: Student, Faculty, Department |
| Available automatically in the platform | Designed manually by developers/admins |
| Mostly fixed structure | Can be customized easily |

---

# 🏫 College Management Data Structure

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

# 🔗 Relationships Between Objects

| Parent | Child | Relationship |
|--------|-------|--------------|
| Department | Student | One-to-Many |
| Department | Faculty | One-to-Many |
| Department | Course | One-to-Many |
| Faculty | Course | One-to-Many |
| Course | Student | One-to-Many |

---

# 🗂 Data Model Overview

```text
Department
   ├── Students
   ├── Faculty
   └── Courses

Faculty
   └── Courses

Course
   └── Students
