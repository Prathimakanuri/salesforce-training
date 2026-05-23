# Salesforce Summer Program - Day 10

## College Management Mini Project

## 1. System Overview

This project is a simple College Management Mini Project developed as part of Day 10 of the Salesforce Summer Program. The main aim of this project is to integrate all the important Salesforce concepts learned so far into one connected mini project.

In this project, a college can manage students, faculty, courses, departments, registrations, attendance, and notifications using Salesforce features like CRM concepts, data modeling, validation rules, formula fields, flows, Apex logic, SOQL, triggers, and Lightning Web Components.

The system is designed to show how a real enterprise application works by connecting the frontend, backend, database, automation, and event-driven logic together.

---

## 2. Goal of Day 10

The goal of Day 10 is to understand how different Salesforce concepts work together in one complete application.

Concepts integrated in this project:

- CRM
- Data Modeling
- Validation Rules
- Formula Fields
- Flows
- Apex
- SOQL
- Triggers
- Lightning Web Components
- UI and Backend Integration

---

## 3. CRM Concepts Used

CRM means Customer Relationship Management. In this project, instead of customers, the system manages college-related people and records.

### Student

A student is a person who registers for courses, attends classes, and receives notifications related to course registration and attendance.

Example fields:

- Student Name
- Email
- Department
- Course Registered
- Attendance Percentage

### Faculty

A faculty member teaches courses and receives notifications when course seats are full or when students have low attendance.

Example fields:

- Faculty Name
- Email
- Department
- Assigned Course

### Course

A course represents a subject or training program offered by the college.

Example fields:

- Course Name
- Course Code
- Maximum Seats
- Registered Students
- Remaining Seats

### Department

A department represents a branch or academic division in the college.

Examples:

- Computer Science
- Electronics
- Mechanical
- Civil

---

## 4. Data Model

The data model defines the objects, fields, and relationships used in the College Management System.

| Object Name | Purpose |
|---|---|
| Student | Stores student details |
| Faculty | Stores faculty details |
| Course | Stores course details |
| Department | Stores department details |
| Registration | Stores course registration details |
| Attendance | Stores student attendance details |

---

## 5. Fields Used

### Student Object Fields

| Field Name | Data Type | Purpose |
|---|---|---|
| Student Name | Text | Stores the name of the student |
| Email | Email | Stores student email address |
| Phone | Phone | Stores contact number |
| Department | Lookup | Connects student with department |
| Course Registered | Lookup | Connects student with course |
| Attendance Percentage | Formula/Number | Shows attendance percentage |

### Faculty Object Fields

| Field Name | Data Type | Purpose |
|---|---|---|
| Faculty Name | Text | Stores faculty name |
| Email | Email | Stores faculty email |
| Department | Lookup | Connects faculty with department |
| Assigned Course | Lookup | Connects faculty with course |

### Course Object Fields

| Field Name | Data Type | Purpose |
|---|---|---|
| Course Name | Text | Stores course name |
| Course Code | Text | Stores unique course code |
| Maximum Seats | Number | Stores total available seats |
| Registered Students | Number | Stores number of registered students |
| Remaining Seats | Formula | Calculates available seats |
| Faculty | Lookup | Connects course with faculty |

### Department Object Fields

| Field Name | Data Type | Purpose |
|---|---|---|
| Department Name | Text | Stores department name |
| Department Code | Text | Stores department code |
| Head of Department | Lookup | Connects department with faculty |

### Registration Object Fields

| Field Name | Data Type | Purpose |
|---|---|---|
| Student | Lookup | Connects registration with student |
| Course | Lookup | Connects registration with course |
| Registration Date | Date | Stores date of registration |
| Status | Picklist | Shows registration status |

### Attendance Object Fields

| Field Name | Data Type | Purpose |
|---|---|---|
| Student | Lookup | Connects attendance with student |
| Course | Lookup | Connects attendance with course |
| Total Classes | Number | Stores total classes conducted |
| Classes Attended | Number | Stores classes attended |
| Attendance Percentage | Formula | Calculates attendance percentage |

---

## 6. Relationships

Relationships connect different objects and make the system meaningful.

| Relationship | Type | Explanation |
|---|---|---|
| Student to Department | Lookup Relationship | One student belongs to one department |
| Faculty to Department | Lookup Relationship | One faculty belongs to one department |
| Course to Faculty | Lookup Relationship | One course is handled by one faculty |
| Student to Course | Lookup Relationship | Student can register for a course |
| Registration to Student | Lookup Relationship | Registration record is connected to student |
| Registration to Course | Lookup Relationship | Registration record is connected to course |
| Attendance to Student | Lookup Relationship | Attendance is tracked for each student |
| Attendance to Course | Lookup Relationship | Attendance is tracked for each course |

---

## 7. Validation Rules

Validation rules are used to maintain correct and clean data in the system. They prevent users from entering invalid information.

### Validation Rule 1: Email Mandatory

Purpose:

Student email should not be empty because email is needed for sending registration confirmations and attendance alerts.

Rule Logic:

If the Email field is blank, the system should show an error.

Error Message:

Email is mandatory for student registration.

### Validation Rule 2: Seats Cannot Exceed Limit

Purpose:

The number of registered students should not be greater than the maximum seats available for the course.

Rule Logic:

If Registered Students is greater than Maximum Seats, the system should show an error.

Error Message:

Registered students cannot exceed the maximum seat limit.

### Validation Rule 3: Attendance Cannot Be More Than Total Classes

Purpose:

Classes attended should not be greater than total classes conducted.

Rule Logic:

If Classes Attended is greater than Total Classes, the system should show an error.

Error Message:

Classes attended cannot be greater than total classes.

---

## 8. Formula Fields

Formula fields are used to automatically calculate values based on other fields.

### Formula Field 1: Remaining Seats

Purpose:

To calculate how many seats are still available in a course.

Formula:

Maximum Seats - Registered Students

Example:

If Maximum Seats = 60 and Registered Students = 45, then Remaining Seats = 15.

### Formula Field 2: Attendance Percentage

Purpose:

To calculate the attendance percentage of a student.

Formula:

(Classes Attended / Total Classes) * 100

Example:

If Classes Attended = 36 and Total Classes = 40, then Attendance Percentage = 90%.

---

## 9. Flow Automation

Flows are used to automate business processes without writing code.

### Flow 1: Auto Confirmation Email

Purpose:

When a student successfully registers for a course, an automatic confirmation email should be sent to the student.

Flow Steps:

1. Student submits course registration.
2. Registration record is created.
3. Flow checks the registration status.
4. If registration is successful, an email is sent to the student.
5. Student receives confirmation message.

Example Email:

Dear Student,

Your course registration has been completed successfully.

Thank you.  
College Management Team

### Flow 2: Attendance Warning

Purpose:

When a student's attendance is below the required percentage, the system should send a warning notification.

Flow Steps:

1. Attendance record is updated.
2. Flow checks the attendance percentage.
3. If attendance is below 75%, warning email is sent.
4. Student gets notified to improve attendance.

Example Email:

Dear Student,

Your attendance is below the required percentage. Please attend classes regularly.

Thank you.  
College Management Team

---

## 10. Apex Logic

Apex is used when business logic becomes complex and cannot be handled only with flows.

### Apex Logic 1: Eligibility Calculation

Purpose:

To check whether a student is eligible based on attendance and course registration status.

Example Logic:

- If attendance is greater than or equal to 75%, the student is eligible.
- If attendance is below 75%, the student is not eligible.

Pseudo Logic:

if attendancePercentage >= 75  
student is eligible  
else  
student is not eligible

### Apex Logic 2: Bulk Operations

Purpose:

To handle many student records at the same time without performance issues.

Example:

If 500 students register for courses at the same time, Apex should process all records efficiently in bulk instead of processing one by one.

### Apex Logic 3: Course Seat Checking

Purpose:

To check whether seats are available before allowing registration.

Example Logic:

if remainingSeats > 0  
allow registration  
else  
show course full message

---

## 11. SOQL Usage

SOQL stands for Salesforce Object Query Language. It is used to retrieve data from Salesforce objects.

### Example 1: Get Students from a Department

SELECT Id, Name, Email__c, Department__c  
FROM Student__c  
WHERE Department__c = 'Computer Science'

### Example 2: Get Course Details

SELECT Id, Name, Maximum_Seats__c, Registered_Students__c, Remaining_Seats__c  
FROM Course__c

### Example 3: Get Low Attendance Students

SELECT Id, Name, Attendance_Percentage__c  
FROM Student__c  
WHERE Attendance_Percentage__c < 75

---

## 12. Trigger and Event Thinking

Triggers are used to perform actions automatically when records are created, updated, or deleted.

### Trigger 1: Notify Faculty When Course Is Full

Purpose:

When the number of registered students reaches the maximum seat limit, the faculty should be notified.

Trigger Logic:

1. Course registration is created.
2. Registered student count is updated.
3. System checks remaining seats.
4. If remaining seats become 0, faculty is notified.

### Trigger 2: Alert for Low Attendance

Purpose:

When attendance percentage becomes low, the system should alert the student or faculty.

Trigger Logic:

1. Attendance record is updated.
2. System calculates attendance percentage.
3. If attendance is below 75%, alert is created.
4. Student and faculty are notified.

---

## 13. Lightning Web Components UI

Lightning Web Components are used to create the frontend user interface of the system.

### UI Screen 1: Student Dashboard

The Student Dashboard shows important information for students.

Features:

- View student profile
- View registered courses
- View attendance percentage
- View notifications
- Register for available courses

### UI Screen 2: Faculty Dashboard

The Faculty Dashboard helps faculty members manage students and courses.

Features:

- View assigned courses
- View registered students
- View low attendance students
- Receive course full alerts
- Manage student attendance

### UI Screen 3: Registration Screen

The Registration Screen allows students to register for courses.

Features:

- Select course
- View available seats
- Submit registration
- Show confirmation message
- Prevent registration if seats are full

---

## 14. Complete Data Flow

Complete flow:

Student clicks Register  
↓  
LWC Registration Screen opens  
↓  
Student selects course and submits form  
↓  
Frontend sends data to backend  
↓  
Validation rules check required fields and seat limit  
↓  
Apex logic checks eligibility and available seats  
↓  
Flow sends confirmation email  
↓  
Trigger checks whether course is full  
↓  
Data is saved into Salesforce database  
↓  
Student and faculty receive notification

### Explanation

When the student clicks the Register button, the Lightning Web Component displays the registration screen. The student selects a course and submits the form. The data entered by the student goes from the frontend to the Salesforce backend.

Before saving the record, validation rules check whether all required fields are filled correctly. For example, the email should not be blank and the course seats should not exceed the limit.

After validation, Apex logic checks whether the student is eligible and whether seats are available. If everything is correct, the registration record is saved in the database.

After saving the record, a flow sends an automatic confirmation email to the student. A trigger also checks whether the course has become full. If the course is full, the faculty is notified.

This shows how LWC, validation rules, Apex, flows, triggers, and database work together in one complete Salesforce application.

---

## 15. Architecture Thinking

Enterprise systems need different layers because each layer has a separate responsibility.

### Frontend

Frontend is the user interface that students and faculty use. In this project, Lightning Web Components are used as the frontend.

Examples:

- Student Dashboard
- Faculty Dashboard
- Registration Screen

### Backend

Backend handles the business logic of the system. Apex is used to process complex logic like eligibility checking and bulk operations.

Examples:

- Checking course seats
- Calculating eligibility
- Processing many records

### Database

Database stores all important records like students, faculty, courses, departments, registration, and attendance.

Examples:

- Student records
- Course records
- Attendance records

### Automation

Automation reduces manual work. Flows are used to send confirmation emails and attendance warning messages automatically.

Examples:

- Auto confirmation email
- Attendance warning email

### Events and Triggers

Events and triggers help the system react immediately when something important happens.

Examples:

- Notify faculty when a course is full
- Alert student when attendance is low

---

## 16. Scaling Thinking

Suppose 50,000 students use this system. The system may face some problems if it is not designed properly.

### Problem 1: Performance

If many students register at the same time, the system may become slow.

Solution:

- Use bulkified Apex code
- Avoid unnecessary queries
- Use proper indexing and optimized SOQL

### Problem 2: Data Consistency

If many students try to register for the same course at the same time, seat count may become incorrect.

Solution:

- Use proper validation
- Use transactions carefully
- Check seat availability before saving records

### Problem 3: Notifications

Sending too many emails or notifications at once may cause limits or delays.

Solution:

- Use asynchronous processing
- Send only necessary notifications
- Avoid duplicate alerts

### Problem 4: Security

Different users should see only the data they are allowed to access.

Solution:

- Use profiles
- Use permission sets
- Use sharing rules
- Apply field-level security

### Problem 5: Governor Limits

Salesforce has limits for SOQL queries, DML operations, and automation.

Solution:

- Write bulk-safe Apex
- Avoid SOQL inside loops
- Use efficient flows and triggers

---

## 17. Why Enterprise Systems Need Modular Architecture

Enterprise systems need modular architecture because large systems are difficult to manage if everything is written together. Modular architecture separates the system into smaller parts like frontend, backend, database, automation, and security.

This makes the system easier to build, test, debug, update, and scale. If one part changes, the entire system does not need to be changed.

Example:

If the registration screen needs improvement, only the LWC component can be updated without changing the entire backend logic.

---

## 18. Why Relationships Are Important

Relationships are important because they connect data between different objects.

For example, a student is connected to a department, a course is connected to a faculty member, and registration is connected to both student and course.

Without relationships, data will be disconnected and difficult to understand. Relationships help in reporting, automation, data retrieval, and real-world business logic.

---

## 19. Why Flows Are Insufficient for Some Cases

Flows are useful for automation, but they are not always enough for complex logic.

Flows may become difficult when:

- Large data processing is required
- Complex calculations are needed
- Bulk operations are involved
- Custom error handling is required
- Advanced logic is needed

In such cases, Apex is better because it gives more control to developers.

---

## 20. Why Systems Need Event-Driven Behavior

Systems need event-driven behavior because some actions should happen automatically when an event occurs.

Example:

When a course becomes full, the faculty should be notified automatically. When attendance becomes low, the student should receive an alert.

This makes the system faster, smarter, and more useful because users do not need to manually check everything.

---

## 21. Why UI and Backend Separation Is Important

UI and backend separation is important because both have different responsibilities.

The UI is responsible for displaying screens and collecting user input. The backend is responsible for processing logic, saving data, and applying business rules.

Benefits:

- Easy maintenance
- Better security
- Reusable backend logic
- Clean application structure
- Easy testing

Example:

The same Apex backend logic can be used by different UI screens like Student Dashboard and Registration Screen.

---

## 22. Why Enterprise Systems Require Testing

Enterprise systems require testing because they handle important business data and many users depend on them.

Testing helps to:

- Find errors early
- Make sure logic works correctly
- Prevent wrong data entry
- Check automation
- Improve system quality
- Avoid failures in real-time usage

In Salesforce, Apex test classes are important to verify code before deployment.

---

## 23. Why Reusable UI Architecture Is Powerful

Reusable UI architecture is powerful because the same component can be used in multiple places.

Example:

A course card component can be reused in:

- Student Dashboard
- Faculty Dashboard
- Course Registration Page

Benefits:

- Saves development time
- Reduces duplicate code
- Makes UI consistent
- Easy to update

---

## 24. What Problems Happen When Systems Scale

When systems scale and many users start using them, several problems can happen.

Common problems:

- Slow performance
- Data inconsistency
- Security issues
- Too many notifications
- Governor limit errors
- Difficult maintenance
- Large data handling issues

To solve these problems, developers should design systems carefully using modular architecture, optimized queries, bulk-safe code, proper security, and good automation design.

---

## 25. Why Automation Should Be Designed Carefully

Automation should be designed carefully because too much automation can create problems.

Possible issues:

- Duplicate emails
- Infinite loops
- Slow performance
- Wrong notifications
- Confusion for users
- Governor limit errors

Good automation should be simple, useful, tested, and designed according to real business needs.

---

## 26. How Salesforce Concepts Integrate Together

Salesforce concepts work together to build a complete enterprise system.

In this project:

- Objects store college data.
- Fields store specific information.
- Relationships connect students, faculty, courses, and departments.
- Validation rules protect data quality.
- Formula fields calculate values automatically.
- Flows automate emails and warnings.
- Apex handles complex logic.
- SOQL retrieves required data.
- Triggers react to record changes.
- LWC displays the user interface.

Together, these concepts create a complete Salesforce application.

---

## 27. Revision Questions and Answers

### 1. Why do enterprise systems need modular architecture?

Enterprise systems need modular architecture because it separates the system into smaller parts like frontend, backend, database, automation, and security. This makes the system easier to build, manage, test, update, and scale.

### 2. Why are relationships important?

Relationships are important because they connect records between different objects. For example, a student can be connected to a department and a course. This helps in data organization, reporting, and automation.

### 3. Why are Flows insufficient for some cases?

Flows are insufficient for some cases because they may not handle complex logic, bulk operations, advanced calculations, or custom error handling easily. Apex is better for complex backend logic.

### 4. Why do systems need event-driven behavior?

Systems need event-driven behavior so that actions can happen automatically when an event occurs. For example, when a course becomes full, the faculty should be notified automatically.

### 5. Why is UI/backend separation important?

UI/backend separation is important because the UI handles user interaction and the backend handles business logic. This makes the system clean, reusable, secure, and easy to maintain.

### 6. Why do enterprise systems require testing?

Enterprise systems require testing to make sure the system works correctly, data is handled safely, automation works properly, and errors are avoided before deployment.

### 7. Why is reusable UI architecture powerful?

Reusable UI architecture is powerful because one component can be used in many places. It saves time, reduces duplicate code, and keeps the user interface consistent.

### 8. What problems happen when systems scale?

When systems scale, problems like slow performance, data inconsistency, notification overload, security issues, and governor limit errors can happen.

### 9. Why should automation be designed carefully?

Automation should be designed carefully because poor automation can cause duplicate actions, wrong emails, infinite loops, performance issues, and confusion for users.

### 10. How do all Salesforce concepts integrate together?

All Salesforce concepts integrate together by connecting data, logic, automation, and UI. Objects store data, relationships connect data, validation rules protect data, flows automate tasks, Apex handles logic, triggers respond to events, and LWC displays the frontend.

---

## 28. Reflection

After learning Salesforce and working on this mini project, I realized that enterprise software systems are not built using only one concept. A real system needs many parts working together.

The frontend allows users to interact with the application. The backend handles business logic. The database stores important records. Automation reduces manual work. Triggers and events help the system react automatically.

I also understood that Salesforce is powerful because it combines low-code tools like flows with code-based tools like Apex and LWC. This makes it useful for both simple and complex business applications.

This project helped me understand how real Salesforce systems are structured and how CRM, data modeling, automation, Apex, SOQL, triggers, and LWC work together in one complete application.

---

## 29. End of Day Outcome

By completing Day 10, I understood:

- Enterprise application architecture
- UI, backend, and data integration
- Automation and event-driven behavior
- Business logic using Apex
- Data retrieval using SOQL
- Modular application design
- How real Salesforce systems are structured
- How all Salesforce concepts connect together in one project

---

## 30. Conclusion

The College Management Mini Project is a simple but complete Salesforce-based application idea that connects all major concepts learned so far. It shows how students, faculty, courses, departments, registration, attendance, automation, backend logic, and UI can work together in one system.

This project helped me understand the importance of designing enterprise applications in a structured, modular, scalable, and secure way.
