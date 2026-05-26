# Salesforce Summer Program – Day 11  
## Testing, Asynchronous Processing, Reliability and Scalability

## Goal of Day 11

The goal of Day 11 is to understand how enterprise systems become reliable, scalable, and safe to use. Until now, we learned how to build systems, automate workflows, create user interfaces, and integrate components. Today, the focus is on enterprise-quality software thinking.

In real-world applications, systems are used by many users at the same time. Because of this, developers must make sure that the system works correctly, handles errors properly, supports large amounts of data, and does not stop working when one task fails. This is why testing, asynchronous processing, reliability, and scalability are very important in enterprise systems.

---

## 1. Why Testing Matters

Testing is the process of checking whether a system works as expected. In enterprise systems, testing is very important because even a small mistake can affect many users, business processes, and data records.

In Salesforce, testing helps developers verify that Apex classes, triggers, workflows, validations, and automation are working correctly. Testing also helps prevent bugs before the application is used by real users.

Testing matters because:

- It helps identify mistakes early.
- It prevents incorrect data from entering the system.
- It improves system reliability.
- It ensures that business rules are followed.
- It helps developers safely update or modify existing features.
- It reduces failure in production systems.
- It improves confidence in the application.
- It ensures that automation works correctly.
- It protects users from system errors.
- It supports enterprise-level software quality.

For example, in a College Management System, if a student enters an invalid email or tries to register twice, testing helps ensure that such issues are detected and prevented.

---

## 2. What is Asynchronous Processing?

Asynchronous processing means running a task in the background instead of executing it immediately while the user is waiting.

In synchronous execution, the user must wait until the task is completed. But in asynchronous execution, the system accepts the request and processes the task later in the background. This improves performance and user experience.

In Salesforce, asynchronous Apex is used to handle background operations such as future methods, queueable Apex, batch Apex, and scheduled Apex.

Asynchronous processing is useful when:

- A task takes a long time to complete.
- A large amount of data needs to be processed.
- The system needs to communicate with an external service.
- The user should not wait for the operation to finish.
- The task can be completed later in the background.

Examples of asynchronous processing include sending bulk emails, generating reports, importing large data, sending notifications, and synchronizing records with external systems.

---

## 3. Important Test Cases for College Management System

Below are 10 important test cases for a College Management System along with the problem each test prevents.

| Test Case No. | Test Case | What Should Be Tested | Problem Prevented |
|---|---|---|---|
| 1 | Invalid Email Validation | Check whether the system rejects incorrect email formats during student registration. | Prevents wrong contact details and communication failures. |
| 2 | Duplicate Student Registration | Check whether the same student can register more than once using the same email or roll number. | Prevents duplicate student records. |
| 3 | Seat Limit Validation | Check whether admissions stop when the course seat limit is reached. | Prevents overbooking of course seats. |
| 4 | Mandatory Fields Check | Check whether required fields like name, email, phone number, and course are filled. | Prevents incomplete student records. |
| 5 | Attendance Below Threshold | Check whether the system identifies students whose attendance is below the required percentage. | Prevents incorrect eligibility decisions. |
| 6 | Fee Payment Update | Check whether payment status is updated correctly after successful payment. | Prevents wrong fee records and confusion. |
| 7 | Failed Payment Handling | Check whether failed payments do not mark the student as paid. | Prevents incorrect payment confirmation. |
| 8 | Notification Failure Handling | Check whether the system handles failed SMS or email notifications properly. | Prevents silent communication failures. |
| 9 | Unauthorized Access | Check whether students, faculty, and admins can access only their allowed pages and records. | Prevents data misuse and privacy issues. |
| 10 | Marks Entry Validation | Check whether marks entered are within the valid range and not negative or above maximum marks. | Prevents incorrect academic results. |

---

## 4. Explanation of Test Cases

### 1. Invalid Email Validation

When a student registers, the system should check whether the email address is in a proper format. If an invalid email is accepted, the college may not be able to send important updates, login details, or notifications to the student.

This test prevents communication failure.

### 2. Duplicate Student Registration

The system should not allow the same student to register multiple times using the same email, phone number, or roll number. Duplicate records can create confusion in admissions, attendance, and fee management.

This test prevents duplicate student data.

### 3. Seat Limit Validation

Every course has a limited number of seats. The system should not allow more students than the available seat count. If this is not tested, more students may be admitted than the college can handle.

This test prevents seat overbooking.

### 4. Mandatory Fields Check

Important fields such as student name, email, phone number, course, and admission number should not be left empty. Without this validation, incomplete data may enter the system.

This test prevents incomplete student records.

### 5. Attendance Below Threshold

The system should identify students whose attendance is below the required limit. This is important for exam eligibility and academic rules.

This test prevents wrong eligibility decisions.

### 6. Fee Payment Update

When a student pays the fee successfully, the system should update the payment status correctly. If this does not work, a student who paid may still be shown as unpaid.

This test prevents incorrect fee records.

### 7. Failed Payment Handling

If a payment fails, the system should not mark it as successful. This is important because wrong payment updates can cause financial and administrative issues.

This test prevents false payment confirmation.

### 8. Notification Failure Handling

The system may send emails or SMS messages for registration, attendance, payment, or exam updates. If a notification fails, the system should record the failure and retry if needed.

This test prevents silent notification failure.

### 9. Unauthorized Access

Only authorized users should access specific information. For example, students should not access admin records, and faculty should not change payment details unless allowed.

This test prevents security and privacy issues.

### 10. Marks Entry Validation

Marks should be entered only within the allowed range. For example, if the maximum marks are 100, the system should not accept 120 or negative marks.

This test prevents incorrect academic results.

---

## 5. Async Use Cases in College Management System

Below are 5 examples where background processing is better than immediate processing.

| Use Case No. | Async Use Case | Why Background Processing is Better |
|---|---|---|
| 1 | Bulk Email Notifications | Sending emails to hundreds of students may take time, so it should run in the background. |
| 2 | Report Generation | Attendance reports, fee reports, and result reports may contain large data and should not block users. |
| 3 | Large Student Data Import | Importing thousands of student records should be processed in the background to avoid system delay. |
| 4 | External System Synchronization | Syncing data with payment gateways, university portals, or external apps may take time. |
| 5 | SMS and App Notifications | Sending notifications to many students should run asynchronously to improve performance. |

---

## 6. Explanation of Async Use Cases

### 1. Bulk Email Notifications

In a College Management System, the admin may need to send emails to all students regarding exams, events, fee reminders, or holidays. Sending all emails immediately can slow down the system. By using asynchronous processing, emails can be sent in the background while the admin continues using the system.

### 2. Report Generation

Reports such as attendance reports, marks reports, fee reports, and admission reports may contain large amounts of data. If the system generates these reports immediately, the user may have to wait for a long time. Background processing allows reports to be generated without blocking the user.

### 3. Large Student Data Import

At the beginning of an academic year, the college may import hundreds or thousands of student records. This process may take time. If done synchronously, the system may freeze or become slow. Asynchronous processing handles the import in the background.

### 4. External System Synchronization

College systems may need to sync data with payment gateways, university databases, or government portals. External systems may respond slowly. Running this process asynchronously avoids delays for the user.

### 5. SMS and App Notifications

Sending SMS or app notifications to many students at once can take time. Background processing ensures that notifications are delivered without affecting the main application performance.

---

## 7. Reliability Discussion

Reliability means the system should work correctly even when errors, failures, or unexpected situations happen. A reliable system protects data and ensures that users can continue their work without major issues.

In a College Management System, reliability is very important because the system handles student registration, attendance, payments, marks, reports, and notifications.

---

## 8. Problems If System Crashes During Important Operations

### 1. Crash During Student Registration

If the system crashes during student registration, the following problems may happen:

- Student data may be saved partially.
- Duplicate records may be created if the student tries again.
- Registration confirmation may not be sent.
- Seat count may be updated incorrectly.
- Admin may not know whether the student was registered or not.

Testing can help by checking whether registration is completed fully or rolled back safely if an error occurs.

### 2. Crash During Payment Update

If the system crashes during payment update, the following problems may happen:

- Payment may be deducted from the student account but not updated in the college system.
- Student may be marked as unpaid even after payment.
- Duplicate payment attempts may happen.
- Fee reports may show incorrect data.
- Admin and student may face confusion.

Testing can help by checking payment success, failure, retry, and rollback scenarios.

### 3. Crash During Attendance Update

If the system crashes during attendance update, the following problems may happen:

- Attendance may be saved for only some students.
- Some students may be incorrectly marked present or absent.
- Attendance percentage may be calculated wrongly.
- Students may lose exam eligibility because of wrong data.
- Faculty may need to repeat the work.

Testing can help by checking whether attendance records are saved correctly and consistently.

---

## 9. How Testing Helps Reliability

Testing helps reliability by making sure the system behaves correctly in normal and failure situations. It checks whether the system follows business rules, handles errors, prevents invalid data, and maintains correct records.

Testing helps in the following ways:

- It checks whether important features work properly.
- It prevents wrong data from being saved.
- It verifies that errors are handled safely.
- It ensures that partial failures do not damage data.
- It confirms that users get proper messages when something goes wrong.
- It helps developers find and fix bugs before deployment.
- It improves trust in the application.
- It supports safe updates and future changes.

---

## 10. Reflection

Enterprise systems require testing, scalability, and asynchronous processing because they are used by many users and handle important business data. Simple direct execution may work for small programs, but it is not suitable for large real-world systems.

Testing is required because enterprise systems must be correct and reliable. Without testing, bugs may affect users, data, payments, reports, and business decisions.

Scalability is required because the number of users and records may increase over time. A system should work properly even when many students, faculty members, and admins use it at the same time.

Asynchronous processing is required because some tasks take more time to complete. If every task runs immediately, the system may become slow and users may have to wait. Background processing helps the system perform long-running tasks without blocking the user.

In a College Management System, tasks such as sending bulk emails, generating reports, importing student records, updating payments, and sending notifications should be handled carefully. These tasks should not disturb the main user experience.

Enterprise software is different from small scripts because enterprise software must be reliable, scalable, secure, and maintainable. It should handle failures, large data, multiple users, and complex business rules.

---

# Revision Questions and Answers

## 1. Why is testing important?

Testing is important because it checks whether the system works correctly. It helps find bugs early, prevents wrong data, improves reliability, and ensures that business rules are followed. In enterprise systems, testing protects users and business operations from errors.

---

## 2. What problems happen without testing?

Without testing, many problems can happen. The system may accept invalid data, create duplicate records, fail during important operations, show wrong reports, allow unauthorized access, or crash unexpectedly. These issues can affect users, business decisions, and data accuracy.

---

## 3. Difference between synchronous and asynchronous execution?

Synchronous execution means the task runs immediately and the user must wait until it is completed. Asynchronous execution means the task runs in the background, so the user does not need to wait.

Example:

Synchronous: A student clicks submit and waits until the entire process finishes.

Asynchronous: A student clicks submit, the system saves the request, and background jobs send emails or notifications later.

---

## 4. Why do enterprise systems use background jobs?

Enterprise systems use background jobs to handle long-running tasks without slowing down the main application. Tasks like bulk emails, large data imports, report generation, and external synchronization are better handled in the background.

Background jobs improve performance, user experience, and system scalability.

---

## 5. Why should developers think about scalability?

Developers should think about scalability because the number of users, records, and transactions may increase in the future. A system that works for 100 users should also be able to support thousands of users with proper design.

Scalability helps the system grow without performance issues.

---

## 6. Why are test cases important?

Test cases are important because they clearly define what should be checked in the system. They help verify whether features are working correctly. Test cases also help developers catch bugs and confirm that changes do not break existing functionality.

---

## 7. What happens when systems fail partially?

Partial failure means only part of the operation is completed and the remaining part fails. This can create inconsistent data.

For example, during fee payment, money may be deducted but the system may not update the payment status. During attendance update, attendance may be saved for only some students.

Partial failures can cause confusion, wrong reports, duplicate work, and loss of trust.

---

## 8. Why do large systems require reliability engineering?

Large systems require reliability engineering because many users depend on them. These systems must continue working even when errors happen. Reliability engineering helps design systems that can handle failures, recover safely, protect data, and provide stable service.

---

## 9. Why should enterprise software avoid blocking operations?

Enterprise software should avoid blocking operations because users should not wait for long-running tasks. If one task blocks the system, performance becomes slow and other users may be affected.

Using asynchronous processing helps avoid blocking operations and keeps the system responsive.

---

## 10. Why is enterprise software different from small scripts?

Enterprise software is different from small scripts because it is used by many users, handles important data, follows business rules, and must be secure, reliable, and scalable.

Small scripts usually solve simple tasks. Enterprise software must handle real-world complexity, failures, integrations, large data, and continuous updates.

---

## Final Day 11 Outcome

After completing Day 11, I understood that enterprise systems require more than just working features. They need testing, asynchronous processing, reliability, and scalability.

I learned why testing is important for preventing bugs and protecting data. I also learned how asynchronous processing helps run long tasks in the background. I understood that reliable systems must handle failures safely and avoid partial data problems.

This day helped me understand the enterprise-quality software mindset required for building real-world Salesforce applications.

---

## Folder Structure

```text
day11-testing-async/
│
└── README.md
