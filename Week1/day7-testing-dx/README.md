# Day 7 - Testing, Asynchronous Apex and Salesforce DX

## Salesforce Summer Program - Day 7

### Topic
Testing in Salesforce, Asynchronous Apex, Salesforce DX, CLI Workflow and Complete System Integration

### System Chosen
College Management System

---

## 1. Why Testing Matters

Testing is very important in enterprise systems because many users depend on the application every day. In Salesforce, testing helps developers check whether the system is working correctly before it is used by real users. If we make changes in validation rules, flows, triggers, or Apex code, testing helps us confirm that the new changes are not breaking the existing functionality.

In a College Management System, testing is useful because important data like student registration, course enrollment, attendance, marks, and notifications must be handled correctly. If there is no testing, wrong student details may be saved, duplicate registrations may happen, course seats may be overbooked, or attendance and marks may be calculated incorrectly.

Salesforce also requires Apex test classes because enterprise applications must be reliable, secure, and bug-free. Testing helps developers prevent errors, improve quality, and build confidence before deploying the application to production.

### Importance of Testing

- It prevents bugs before deployment.
- It checks whether business rules are working correctly.
- It ensures that validation rules, flows, triggers, and Apex code work together.
- It improves system reliability.
- It protects real user data from incorrect processing.
- It helps teams make changes safely in large projects.

---

## 2. What is Asynchronous Apex?

Asynchronous Apex is a way of running Apex code in the background instead of running it immediately in the same process. In normal synchronous processing, the user waits until the task is completed. But in asynchronous processing, long-running tasks are moved to the background, so the user can continue working without delay.

Asynchronous Apex is useful when the system needs to perform time-consuming operations such as sending bulk emails, processing large records, generating reports, or synchronizing data with external systems.

In Salesforce, asynchronous processing helps improve performance and user experience. It is mainly used when immediate response is not required.

### Examples of Asynchronous Apex

- Future Methods
- Queueable Apex
- Batch Apex
- Scheduled Apex

### Why Asynchronous Apex is Useful

- It reduces waiting time for users.
- It handles large data processing.
- It improves system performance.
- It avoids timeout errors.
- It is useful for background jobs.
- It helps in integrations with external systems.

### Example in College Management System

When many students register for different courses, the system may need to send confirmation emails to all students. Instead of sending emails immediately and making the user wait, Salesforce can process the email sending in the background using asynchronous Apex.

---

## 3. What is Salesforce DX?

Salesforce DX means Salesforce Developer Experience. It is a modern development approach provided by Salesforce for professional developers and teams. Salesforce DX helps developers build, test, manage, and deploy Salesforce applications in a structured way.

Instead of making all changes directly in the browser, developers can use Salesforce DX with Visual Studio Code, GitHub, and Salesforce CLI. This makes the development process more professional and team-friendly.

Salesforce DX supports source-driven development. This means code and configuration changes can be stored in files, tracked in GitHub, reviewed by team members, and deployed safely.

### Benefits of Salesforce DX

- It supports professional development workflow.
- It helps developers work with source code.
- It allows version control using GitHub.
- It supports team collaboration.
- It makes deployment easier.
- It works with Salesforce CLI and VS Code.
- It helps maintain clean and organized project structure.

### Why Developers Use Salesforce DX

Developers use Salesforce DX because real-time enterprise projects are handled by teams. Many developers may work on the same Salesforce application. DX helps them manage changes properly, avoid conflicts, track updates, and deploy changes safely.

---

## 4. Complete System Workflow

### College Management System - End-to-End Workflow

In my College Management System, the complete workflow starts when a student registers for a course. The system collects student details such as name, email, phone number, course name, department, year, and registration information. After the student submits the form, different Salesforce features work together to process the data correctly.

### Step 1: Student Registration

The student first enters their details in the registration form. This data is stored in Salesforce as a student record. The form may include fields like Student Name, Email, Phone Number, Course, Department, Year, and Registration Date.

Example:
A student named Ravi registers for a Java Full Stack course in the CSE department.

---

### Step 2: Validation Rules Check the Data

After the student submits the form, validation rules check whether the entered data is correct or not. For example, the email should be in a proper format, the phone number should not be empty, and the course field must be selected.

If the student enters invalid data, the system shows an error message and does not save the record. This helps maintain clean and correct data.

Example:
If the student leaves the email field empty, the validation rule will stop the record from saving.

---

### Step 3: Flow Sends Confirmation

After the record is saved successfully, Salesforce Flow automatically sends a confirmation message or email to the student. This confirmation tells the student that their course registration has been completed successfully.

Example:
The student receives a message like:
"Your registration for Java Full Stack course is completed successfully."

---

### Step 4: Trigger Updates Course Count

After the student registration is completed, an Apex Trigger updates the number of students enrolled in that course. This helps the college track how many students have registered for each course.

Example:
If the Java Full Stack course already has 25 students and one new student registers, the trigger updates the count to 26.

---

### Step 5: Formula Field Recalculates Available Seats

A formula field automatically calculates the remaining seats in the course. It can subtract the number of registered students from the total available seats.

Formula Example:
Available Seats = Total Seats - Registered Students

Example:
If total seats are 60 and registered students are 26, available seats will be 34.

---

### Step 6: Platform Event Sends Notification

A Platform Event can be used to send notifications when an important action happens. For example, if a course is almost full, the system can notify the admin or course coordinator.

Example:
If only 5 seats are left in a course, the system sends a notification to the admin.

---

### Step 7: Database Stores Records

All student registration details, course details, attendance details, and enrollment details are stored in the Salesforce database. This helps the college maintain organized and secure data.

Example:
Student records, course records, and registration records are stored and can be searched anytime.

---

### Step 8: Reports Show Analytics

Salesforce Reports and Dashboards help the college understand important information. Admins can view how many students registered, which courses are popular, how many seats are left, and which department has more registrations.

Example Reports:
- Total students registered
- Course-wise student count
- Department-wise enrollment
- Available seats report
- Monthly registration report

---

### Complete Workflow Summary

Student registers for a course  
→ Validation Rules check the entered data  
→ Record is saved in Salesforce  
→ Flow sends confirmation email  
→ Apex Trigger updates course enrollment count  
→ Formula Field calculates available seats  
→ Platform Event sends notification if needed  
→ Database stores all records  
→ Reports and Dashboards show analytics  

This complete workflow shows how different Salesforce concepts like Validation Rules, Flows, Triggers, Formula Fields, Platform Events, Database, Reports, and Dashboards work together in one real-time College Management System.

---

## 5. Important Test Cases

Testing is very important in the College Management System because even small mistakes can affect student data, course registration, attendance, and reports. Below are important test cases that must be tested.

---

### Test Case 1: Invalid Email Format

#### What should be tested?
The system should check whether the student email is entered in a valid format.

#### Example
Correct Email: student@gmail.com  
Wrong Email: studentgmail.com

#### What problem could happen if not tested?
If invalid email addresses are saved, students may not receive confirmation emails, course updates, or important notifications. This can create communication problems between the college and students.

---

### Test Case 2: Duplicate Student Registration

#### What should be tested?
The system should check whether the same student is registering multiple times for the same course.

#### Example
A student should not be allowed to register twice for the same Java Full Stack course.

#### What problem could happen if not tested?
If duplicate registrations are allowed, course count will become incorrect, seats may be wrongly reduced, and reports will show wrong enrollment numbers.

---

### Test Case 3: Course Overbooking

#### What should be tested?
The system should check whether course registration stops after all seats are filled.

#### Example
If a course has only 60 seats, the 61st student should not be allowed to register.

#### What problem could happen if not tested?
If overbooking happens, more students may register than the available capacity. This creates management issues and students may face problems during course allocation.

---

### Test Case 4: Attendance Calculation

#### What should be tested?
The system should correctly calculate student attendance percentage based on total classes and attended classes.

#### Example
If total classes are 40 and the student attended 32 classes, attendance should be calculated as 80%.

#### What problem could happen if not tested?
If attendance calculation is wrong, students may be marked incorrectly as eligible or not eligible. This can affect academic decisions.

---

### Test Case 5: Trigger Execution

#### What should be tested?
The Apex Trigger should correctly update the course enrollment count whenever a student registers or cancels registration.

#### Example
If one student registers, the course count should increase by 1. If one student cancels, the course count should decrease by 1.

#### What problem could happen if not tested?
If the trigger does not work properly, course count and available seats will become incorrect. This can affect reports and course planning.

---

### Test Case 6: Confirmation Flow

#### What should be tested?
The Salesforce Flow should send a confirmation email or message after successful registration.

#### Example
After registration, the student should receive a confirmation message.

#### What problem could happen if not tested?
If the confirmation flow fails, students may not know whether their registration is completed or not.

---

### Test Case 7: Required Fields

#### What should be tested?
The system should make important fields mandatory, such as Student Name, Email, Course, Department, and Phone Number.

#### Example
A student should not be able to submit the form without selecting a course.

#### What problem could happen if not tested?
Incomplete student records may be saved, which creates confusion and reduces data quality.

---

## 6. Async Thinking - Background Processing Examples

Asynchronous processing is better than immediate processing when the task takes more time or does not need to be completed instantly.

---

### Example 1: Sending Bulk Emails

If hundreds of students register for courses, the system may need to send confirmation emails to all of them. Sending emails immediately can slow down the system. So, it is better to send bulk emails in the background using asynchronous processing.

---

### Example 2: Large Report Generation

The college may generate large reports such as department-wise student registrations, attendance reports, or course-wise enrollment reports. These reports may take time to process. So, background processing is better because users do not need to wait.

---

### Example 3: Data Synchronization

The College Management System may need to sync data with another external system, such as a university portal or payment system. This process may take time, so asynchronous processing is useful for handling it in the background.

---

## 7. Developer Workflow Reflection

Professional developers use GitHub, Salesforce DX, and CLI instead of only browser clicks because enterprise software development needs structure, teamwork, tracking, and safe deployment.

---

### Why Developers Use GitHub

GitHub is used for version control and collaboration. It helps developers store their code, track changes, and work with team members. If any mistake happens, developers can check previous versions and fix the issue.

In a team project, many developers may work on different features. GitHub helps manage all changes safely.

#### Benefits of GitHub

- Tracks code changes
- Supports teamwork
- Helps review code
- Maintains project history
- Allows rollback to previous versions
- Makes project sharing easier

---

### Why Developers Use Salesforce DX

Salesforce DX gives a professional development experience. It allows developers to work with Salesforce projects using source code, VS Code, GitHub, and CLI. It supports source-driven development, which is very useful in enterprise projects.

#### Benefits of Salesforce DX

- Supports modern Salesforce development
- Helps manage metadata and code
- Works with VS Code
- Supports GitHub integration
- Makes deployment easier
- Useful for team-based projects

---

### Why Developers Use CLI

CLI means Command Line Interface. Salesforce CLI helps developers perform tasks using commands instead of doing everything manually in the browser. Developers can create projects, authorize orgs, retrieve metadata, deploy changes, and run tests using CLI.

#### Benefits of CLI

- Saves time
- Improves productivity
- Supports automation
- Helps retrieve and deploy code
- Works well with VS Code
- Useful for professional development workflow

---

## 8. Why Enterprise Software Development Needs Structured Workflows

Enterprise software development needs structured workflows because large applications are used by many users and handle important business data. Without a structured workflow, developers may make random changes, lose track of updates, create bugs, or affect existing features.

In Salesforce, structured workflows help developers plan, build, test, review, and deploy changes safely. Testing ensures that the system works correctly. GitHub tracks all changes. Salesforce DX supports source-driven development. CLI improves productivity. Together, these tools help developers build reliable enterprise applications.

A structured workflow is important because:

- It improves software quality.
- It reduces bugs.
- It helps teams collaborate.
- It makes deployment safer.
- It maintains project history.
- It supports testing before production.
- It makes development professional and organized.

In my College Management System, structured workflow is important because student registrations, course details, attendance, reports, and notifications must work correctly. If there is no proper workflow, wrong data may be stored, students may not receive notifications, and reports may become inaccurate.

So, enterprise software development needs testing, GitHub, Salesforce DX, CLI, and proper development process to build reliable, scalable, and professional applications.

---

## 9. Revision Questions and Answers

### 1. Why are tests important in enterprise systems?

Tests are important because enterprise systems are used by many users and handle important data. Testing helps prevent bugs, checks business logic, and ensures that the system works correctly before deployment.

---

### 2. What problems happen without testing?

Without testing, the system may save wrong data, allow duplicate records, calculate values incorrectly, fail to send notifications, or break existing features after new changes.

---

### 3. Why is asynchronous processing useful?

Asynchronous processing is useful because it runs long tasks in the background. It improves performance and allows users to continue working without waiting for time-consuming operations.

---

### 4. Difference between synchronous and asynchronous processing?

Synchronous processing runs immediately and the user must wait until the task is completed. Asynchronous processing runs in the background and the user does not need to wait for the task to finish.

---

### 5. Why do developers use version control?

Developers use version control to track code changes, manage project history, collaborate with team members, and restore previous versions if mistakes happen.

---

### 6. Why is GitHub important?

GitHub is important because it helps developers store code, track changes, collaborate with teams, review code, and manage projects professionally.

---

### 7. Why is DX useful for teams?

Salesforce DX is useful for teams because it supports source-driven development, GitHub integration, VS Code development, and organized deployment workflow.

---

### 8. How do Flows, Triggers and Validation Rules work together?

Validation Rules check whether the data entered by the user is correct. Flows automate business processes like sending emails or updating records. Triggers execute custom logic using Apex when records are inserted, updated, or deleted. Together, they help automate and control the system properly.

---

### 9. Why should business logic be tested carefully?

Business logic should be tested carefully because it controls important rules of the system. If business logic fails, the system may calculate wrong values, update wrong records, or allow invalid actions.

---

### 10. Why is developer workflow important in large teams?

Developer workflow is important in large teams because many developers work on the same project. A proper workflow avoids confusion, tracks changes, reduces conflicts, and helps deploy changes safely.

---


## 11. Learnings from Today

Today I learned why testing is important in enterprise systems and how it helps prevent bugs. I understood that Salesforce testing is required to make applications reliable and safe before deployment. I also learned about Asynchronous Apex and why background processing is useful for long-running tasks. I understood the basics of Salesforce DX and how it helps developers work professionally using source-driven development. I also learned why GitHub and CLI are important in real-world Salesforce projects.

---

## 12. Doubts / Questions

- How to write Apex test classes properly?
- When should we use Future Methods and when should we use Queueable Apex?
- How to connect Salesforce DX with GitHub in a real project?
- How to deploy Salesforce metadata using CLI?
- How to test Flows and Triggers together?

---

## Conclusion

Day 7 helped me understand how Salesforce development works in real enterprise projects. Testing, Asynchronous Apex, Salesforce DX, GitHub, and CLI are very important for building reliable and professional Salesforce applications. I also understood how different Salesforce concepts like Validation Rules, Flows, Triggers, Formula Fields, Platform Events, Database, Reports, and Dashboards work together in a complete College Management System.
