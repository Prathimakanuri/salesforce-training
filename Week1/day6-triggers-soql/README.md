# Salesforce Summer Program – Day 6
## SOQL, Apex Triggers, and Event-Driven Systems

---

## Notes from Today

Today I learned about how Salesforce stores and retrieves data using queries, how automation happens using Apex Triggers, and why enterprise systems need to react automatically when data changes.

The main topics covered today are SOQL, SOSL, DML operations, querying data, Apex Triggers, Before and After Triggers, Flow vs Trigger, and event-driven behavior in enterprise systems.

---

## 1. What is SOQL?

SOQL stands for Salesforce Object Query Language.

SOQL is used to retrieve data from Salesforce objects. It is similar to SQL, but it is specially designed for Salesforce. In Salesforce, data is stored in objects like Account, Contact, Student, Course, Faculty, etc. SOQL helps us fetch records from these objects based on conditions.

For example, in a College Management System, if we want to find all students who joined a particular course, we can use a query. SOQL allows developers to search and retrieve only the required data instead of manually checking every record.

Simple Example:

SELECT Name, Email FROM Student__c WHERE Course__c = 'Computer Science'

This query means finding the student name and email from the Student object where the course is Computer Science.

SOQL is important because enterprise systems store a large amount of data. Developers need queries to quickly find, filter, and use the required information. Without queries, it becomes difficult to manage records efficiently.

---

## 2. What is an Apex Trigger?

An Apex Trigger is a piece of Apex code that runs automatically when a record is inserted, updated, deleted, or undeleted in Salesforce.

Triggers are used when we want Salesforce to automatically perform an action before or after data changes.

For example, in a College Management System, when a new student registers, the system can automatically send a welcome email or create an admission record. This automatic action can be handled using a trigger.

If a new Student record is created, an Apex Trigger can automatically send a welcome email, assign the student to a department, create a fee record, and notify the class coordinator.

Apex Triggers are used when the automation logic is complex and cannot be easily handled using simple Salesforce Flows. They are useful for advanced business rules, bulk updates, validations, and integrations.

---

## 3. Difference Between Flow and Apex Trigger

| Flow | Apex Trigger |
|---|---|
| Flow is a declarative automation tool. | Apex Trigger is a programmatic automation tool. |
| It can be created using clicks without writing code. | It requires Apex coding knowledge. |
| It is best for simple automation like sending emails or updating fields. | It is best for complex logic and advanced automation. |
| Easier for admins and beginners. | Mainly used by developers. |
| Good for simple business processes. | Good for complex calculations, bulk processing, and integrations. |

Flow should be used when the requirement is simple and can be completed with clicks.

Examples of Flow usage:
- Sending an email notification
- Updating a field
- Creating a simple task
- Sending reminders

Apex Trigger should be used when the logic is complex and needs coding.

Examples of Apex Trigger usage:
- Complex fee eligibility check
- Updating many related records
- Performing calculations on multiple objects
- Calling an external API
- Handling bulk data operations

---

## 4. Difference Between Before Trigger and After Trigger

| Before Trigger | After Trigger |
|---|---|
| Runs before the record is saved to the database. | Runs after the record is saved to the database. |
| Used to update or validate values before saving. | Used to perform actions after the record is saved. |
| The record ID may not be available before insert. | The record ID is available after insert. |
| Commonly used for validation and field updates. | Commonly used for related record updates, emails, and notifications. |

Example of Before Trigger:

Before saving a student record, check whether the phone number or email is entered correctly.

Example of After Trigger:

After a student registration is completed, send a welcome email and create a fee record.

---

## 5. Trigger Use Cases in College Management System

Below are 5 cases where actions should happen automatically after data changes in a College Management System.

---

### Use Case 1: Student Registration Completed

Event:
A new student record is created.

Automatic Action:
The system sends a welcome email to the student.

Explanation:
When a student completes registration, the system should automatically welcome the student and share basic details like login information, course details, and next steps.

Best Automation:
Flow

Reason:
This is a simple email notification, so Flow is enough.

---

### Use Case 2: Course Becomes Full

Event:
A course record is updated and the number of enrolled students reaches the maximum limit.

Automatic Action:
The system sends a notification to the faculty and prevents further enrollment.

Explanation:
When a course is full, the faculty should be informed automatically. This avoids manual checking and helps the college manage course capacity properly.

Best Automation:
Apex Trigger

Reason:
This may require checking student count, updating course status, and preventing extra enrollments. So Apex Trigger is better for this complex logic.

---

### Use Case 3: Student Attendance Drops Below 75%

Event:
A student attendance record is updated.

Automatic Action:
The system sends a warning notification to the student and class coordinator.

Explanation:
If a student’s attendance falls below 75%, the system should automatically warn the student. This helps students take action before they become ineligible for exams.

Best Automation:
Flow or Apex Trigger

Reason:
If it is only sending a simple email, Flow is enough. But if attendance is calculated from many records, Apex Trigger is better.

---

### Use Case 4: Fee Payment Completed

Event:
A fee payment record is updated as Paid.

Automatic Action:
The system automatically updates the student fee status and sends a receipt.

Explanation:
When a student pays the fee, the system should automatically update the fee status. This reduces manual work for the accounts department.

Best Automation:
Apex Trigger

Reason:
This may involve updating related student records, generating receipt details, and checking pending dues. So Apex Trigger is suitable.

---

### Use Case 5: Faculty Assigned to a Course

Event:
A course record is updated with a faculty member.

Automatic Action:
The system notifies the faculty and updates the faculty workload.

Explanation:
When a faculty member is assigned to a course, the system should automatically inform them and update their workload. This helps avoid confusion in academic planning.

Best Automation:
Apex Trigger

Reason:
This involves updating related records and checking workload limits, so Apex Trigger is better.

---

## 6. Flow vs Trigger Thinking

### 1. Simple Email Notification

Best Option:
Flow

Why:
A simple email notification does not require complex coding. It can be created using Salesforce Flow with clicks.

---

### 2. Complex Fee Eligibility Check

Best Option:
Apex Trigger

Why:
Fee eligibility may depend on multiple conditions like scholarship, attendance, category, previous dues, and payment history. Since this logic is complex, Apex Trigger is better.

---

### 3. Updating Related Records

Best Option:
Apex Trigger

Why:
When one record changes, many related records may also need to be updated. Apex Trigger is better for handling related records, especially when many records are involved.

---

### 4. External API Integration

Best Option:
Apex Trigger

Why:
External API integration usually needs coding, authentication, error handling, and response processing. Apex Trigger is more suitable for this type of advanced automation.

---

## 7. Query Examples in Simple English

These are simple English query ideas for a College Management System.

Student Queries:

1. Find all students enrolled in the Computer Science course.
2. Find students whose attendance is below 75%.
3. Find students who have not paid their semester fee.
4. Find all first-year students in the college.
5. Find students who registered this month.

Course Queries:

1. Find all courses handled by Faculty X.
2. Find all courses that are currently full.
3. Find courses with more than 60 students enrolled.
4. Find all courses available for second-year students.
5. Find courses that do not have a faculty assigned yet.

Faculty Queries:

1. Find all faculty members from the CSE department.
2. Find faculty members who are handling more than three courses.
3. Find faculty members assigned to Course A.
4. Find faculty members who are currently available.
5. Find the department head of each department.

Attendance Queries:

1. Find students with attendance below 75%.
2. Find students with attendance above 90%.
3. Find attendance records of a student for this semester.
4. Find students who were absent for more than five classes.
5. Find course-wise attendance percentage.

Fee Queries:

1. Find students who have pending fee payments.
2. Find students who completed full fee payment.
3. Find students who received scholarships.
4. Find fee records updated this week.
5. Find students who paid fees after the due date.

---

## 8. Reflection: Why Enterprise Systems Need Event-Driven Behavior

Enterprise systems need event-driven behavior because business processes should react immediately when important data changes. In large organizations, it is not practical for people to manually check every record and take action. Event-driven systems help automate actions based on events like record creation, update, deletion, or status change.

For example, in a College Management System, when a student registers, the system can automatically send a welcome email. When attendance drops below 75%, the system can send a warning. When a course becomes full, the system can notify the faculty. These automatic actions save time, reduce human errors, and improve efficiency.

Event-driven behavior makes enterprise systems faster, smarter, and more reliable. It helps organizations respond to changes immediately and maintain smooth business operations.

---

## 9. Reflective Questions

### 1. Why do systems need triggers?

Systems need triggers to perform automatic actions when data changes. Triggers help reduce manual work and make sure important actions happen at the right time.

For example, when a student fee status changes to paid, the system can automatically update the student record and send a receipt.

---

### 2. Difference between polling and event-driven systems

Polling means the system repeatedly checks whether something has changed.

Event-driven means the system automatically reacts when a change happens.

| Polling | Event-Driven |
|---|---|
| System checks again and again. | System reacts only when an event happens. |
| Can waste time and resources. | Faster and more efficient. |
| Example: Checking every hour for new registrations. | Example: Sending an email immediately after registration. |

Event-driven systems are better for enterprise applications because they respond immediately and reduce unnecessary checking.

---

### 3. Why are database queries important?

Database queries are important because they help retrieve required data from a large amount of stored information. In enterprise systems, thousands or millions of records may exist. Queries help users and developers find only the needed records.

For example, a college admin may need to find all students with attendance below 75%. Instead of checking every student manually, a query can quickly return the required list.

---

### 4. When should Flows be preferred over Triggers?

Flows should be preferred when the automation is simple and can be completed without code.

Examples:
- Sending email notifications
- Updating simple fields
- Creating tasks
- Sending reminders
- Simple approval processes

Flows are easier to maintain and can be created using clicks. So, if the requirement is simple, Flow is better than writing Apex code.

---

### 5. What problems happen if automation logic becomes too complex?

If automation logic becomes too complex, the system may become difficult to understand, debug, and maintain. Too many automations can also slow down performance or cause unexpected errors.

Problems may include:
- Conflicting automation rules
- Difficult debugging
- Slow system performance
- Duplicate updates
- Wrong notifications
- Hard maintenance for developers and admins

That is why automation should be planned carefully.

---

### 6. Why should developers think carefully before automating actions?

Developers should think carefully before automating actions because automation directly affects business data and users. A wrong automation can update incorrect records, send wrong emails, or create duplicate data.

Before automating, developers should understand:
- What event starts the automation
- What records will be affected
- Whether the logic is simple or complex
- Whether Flow or Trigger is better
- What errors may happen
- How the automation will behave with multiple records

Careful planning helps create reliable and safe automation.

---

## Learnings

From today's task, I learned that Salesforce uses SOQL to retrieve data from objects. I also understood that Apex Triggers are used to automatically run logic when records are inserted, updated, deleted, or undeleted.

I learned that Flow is useful for simple automation, while Apex Trigger is useful for complex automation. I also understood the difference between Before Trigger and After Trigger.

The most important learning is that enterprise systems need event-driven behavior so that they can react automatically to data changes.

---

## Doubts / Questions

1. When should I choose Apex Trigger instead of Flow?
2. How can I write SOQL queries correctly in real projects?
3. How can I avoid creating too many automations in Salesforce?
4. How can triggers be tested before using them in real business systems?

---

## End of Day Outcome

By completing Day 6, I understood:

- How Salesforce queries data
- What SOQL is
- What Apex Triggers are
- Difference between Flow and Trigger
- Difference between Before and After Trigger
- How event-driven systems work
- Why enterprise systems react automatically to data changes

---
