# Salesforce Summer Program - Day 4  
## Flow Builder and Business Process Automation

## 1. What is Flow Builder?

Flow Builder is a no-code automation tool in Salesforce. It is used to automate business processes without writing code. Using Flow Builder, we can collect information, create records, update records, send emails, show screens, and apply business logic using simple drag-and-drop elements.

Flow Builder helps companies reduce repetitive manual work. It makes business processes faster, more accurate, and more consistent.

---

## 2. Types of Flows

### Screen Flow

A Screen Flow is a type of flow that requires user interaction. It displays screens to the user and collects information step by step.

Example:  
In a College Management System, a Screen Flow can be used for student registration. The student enters details like name, email, phone number, and selected course. After submitting the form, Salesforce can create a student record automatically.

### Record-Triggered Flow

A Record-Triggered Flow runs automatically when a record is created, updated, or deleted. It does not need user interaction.

Example:  
In a College Management System, when a new student admission record is created, a Record-Triggered Flow can automatically send a confirmation email and update the admission status.

---

## 3. Automation Ideas for College Management System

### 1. Auto Email After Student Registration

When a student registers for admission, Salesforce can automatically send a confirmation email to the student.

Why automation helps:  
It saves staff time and gives quick confirmation to students.

### 2. Auto Generate Student ID

When a new student record is created, the system can automatically generate a unique student ID.

Why automation helps:  
It avoids manual mistakes and keeps student records organized.

### 3. Auto Update Remaining Seats

When a student joins a course, the system can automatically reduce the available seat count for that course.

Why automation helps:  
It keeps seat availability updated in real time.

### 4. Notify Faculty When Course Is Full

When all seats in a course are filled, Salesforce can automatically notify the faculty or admin.

Why automation helps:  
It helps faculty and admin take quick action, such as closing admissions or opening a new batch.

### 5. Fee Payment Reminder

Before the fee payment deadline, Salesforce can automatically send reminders to students who have not paid their fees.

Why automation helps:  
It reduces manual follow-up work and helps students pay fees on time.

---

## 4. Flow Diagram

### Selected Automation Process: Auto Email After Student Registration

```text
Start
  |
  v
New Student Registration Record Created
  |
  v
Check Student Email Field
  |
  v
Decision: Is Email Available?
  |
  |--- Yes ---> Send Confirmation Email to Student
  |
  |--- No ----> Notify Admin to Update Email
  |
  v
Update Registration Status as "Confirmed"
  |
  v
End
```

### Explanation

In this flow, the process starts when a new student registration record is created. The system checks whether the student email is available or not. If the email is available, Salesforce automatically sends a confirmation email to the student. If the email is not available, the system notifies the admin to update the email. Finally, the registration status is updated as confirmed.

---

## 5. Manual vs Automated Process

### Process Chosen: Student Registration Confirmation

### Manual Process

In the manual process, college staff collect student registration details and enter them into the system. After that, they manually check the details and send a confirmation email or message to the student.

### Problems in Manual Process

- It takes more time.
- Staff may forget to send confirmation.
- Human errors can happen while entering data.
- Students may not get updates quickly.
- It becomes difficult when many students register at the same time.

### Automated Process Using Salesforce

Using Salesforce automation, when a student registration record is created, the system automatically checks the details and sends a confirmation email. It can also update the registration status without manual work.

### How Salesforce Automation Improves It

- Saves time.
- Reduces human errors.
- Sends instant confirmation.
- Improves student experience.
- Helps staff focus on important work instead of repetitive tasks.

---

## 6. Reflection: Why Automation Matters in Enterprise Systems

Automation is very important in enterprise systems because companies handle many repeated tasks every day. If employees do all these tasks manually, it takes more time and mistakes can happen.

Automation helps businesses complete work faster and more accurately. It also improves consistency because the same process is followed every time. Salesforce Flow Builder is useful because it allows companies to automate workflows without writing code.

In a College Management System, automation can help with student registration, fee reminders, seat updates, email notifications, and student ID generation. This reduces manual workload and improves the overall efficiency of the system.

Automation matters because it saves time, improves productivity, reduces errors, and helps organizations provide better service to users.
