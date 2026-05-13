# Salesforce Summer Program - Day 5  
## Apex Introduction

## Goal of the Day

The goal of Day 5 is to understand why Apex is used in Salesforce, how it supports business logic, and how it works along with declarative tools like Flows, validation rules, formulas, and objects.

By the end of this task, I learned:

- What Apex is
- Why Salesforce needs programming along with clicks and configuration
- Basic Apex syntax and logic
- Difference between declarative and programmatic development
- How Apex connects to real business logic
- Where Apex is needed in enterprise applications

---

## 1. What is Apex?

Apex is a programming language used in Salesforce to write custom business logic. It is similar to Java and is used when normal clicks, configuration, validation rules, formulas, or flows are not enough to solve complex business requirements.

Salesforce provides many no-code and low-code tools, but some business problems need custom programming. In such cases, developers use Apex to create advanced logic, automate complex processes, work with database records, and integrate Salesforce with external systems.

Apex can be used for:

- Writing custom business rules
- Performing database operations
- Creating triggers
- Working with SOQL queries
- Handling complex calculations
- Connecting Salesforce with external applications
- Building logic that cannot be achieved easily using Flow

In simple words, Apex helps developers add extra power and flexibility to Salesforce.

---

## 2. Difference Between Flow and Apex

| Flow | Apex |
|---|---|
| Flow is a no-code or low-code automation tool. | Apex is a programming language used in Salesforce. |
| It is created using clicks and drag-and-drop components. | It is created by writing code. |
| It is best for simple and medium-level automation. | It is best for complex business logic. |
| It is easier for admins and beginners. | It requires programming knowledge. |
| It can automate record updates, emails, approvals, and notifications. | It can handle advanced calculations, integrations, triggers, and custom logic. |
| Flow is easier to maintain for simple processes. | Apex is more flexible for complex enterprise requirements. |
| Example: Send email when a student is registered. | Example: Calculate fee discount using multiple conditions and external data. |

### Example

If a student registers for a course and we only want to send a confirmation email, Flow is enough.

But if we need to check seat availability, verify eligibility, calculate fee, apply scholarship, and connect to a payment system, Apex is better.

---

## 3. Difference Between Configuration and Coding

| Configuration | Coding |
|---|---|
| Configuration means building functionality using Salesforce setup tools. | Coding means writing custom logic using programming languages like Apex. |
| It uses clicks instead of code. | It requires programming knowledge. |
| Examples: Objects, fields, validation rules, formulas, flows, page layouts. | Examples: Apex classes, triggers, test classes, integrations. |
| It is faster for simple requirements. | It is useful for complex and advanced requirements. |
| It is easier to modify by admins. | It is usually handled by developers. |
| It is best for standard business processes. | It is best for custom business processes. |

### Example

Creating a required email field for a Student object is configuration.

Writing logic to calculate final eligibility based on marks, attendance, fee status, and seat availability is coding.

---

## 4. Real Examples Where Apex Is Needed

### Example 1: Complex Fee Calculation

In a College Management System, the fee for a student may depend on many conditions like course type, scholarship, category, late fee, hostel fee, transport fee, and previous payment history.

A simple Flow may become too long and difficult to manage if many conditions are added.

Apex is needed because it can handle complex calculations in a clean and reusable way.

#### Why Flow is not enough?

Flow is good for simple conditions, but complex fee calculation may require many if-else conditions, loops, database queries, and reusable methods. Apex handles this better.

---

### Example 2: Integration with External Payment System

A college may use an external payment gateway to collect student fees. Salesforce may need to send student fee details to the payment system and receive payment status back.

Apex is needed to connect Salesforce with external systems using APIs.

#### Why Flow is not enough?

Flow can perform some integrations, but for advanced API handling, error handling, authentication, and response processing, Apex is more suitable.

---

### Example 3: Advanced Student Eligibility Logic

A student may be eligible for a course only if they satisfy multiple rules such as:

- Minimum attendance should be 75%
- Required prerequisites should be completed
- Previous semester marks should be above minimum percentage
- Fees should be cleared
- Course seats should be available

Apex is needed to check all these conditions together and decide whether the student can register.

#### Why Flow is not enough?

Flow can check simple eligibility, but advanced logic with multiple conditions, records, and calculations becomes difficult to maintain in Flow. Apex makes the logic more structured and flexible.

---

## 5. Integrated College Management System Design

For this task, I am connecting all the concepts learned till now with my College Management System.

---

### 5.1 CRM Concept

In Salesforce, CRM is used to manage relationships and processes. In my College Management System, CRM can be used to manage the student admission pipeline.

The admission process can be tracked from enquiry to admission confirmation.

Example flow:

Lead → Student Application → Admission Review → Course Enrollment → Confirmed Student

This helps the college manage student details, communication, admission status, and course registration in one place.

---

### 5.2 Objects

Objects are used to store data in Salesforce. In my College Management System, the main objects are:

| Object | Purpose |
|---|---|
| Student | Stores student details such as name, email, phone, course, attendance, and admission status. |
| Course | Stores course details such as course name, duration, fee, and available seats. |
| Faculty | Stores faculty details such as name, department, email, and assigned course. |
| Enrollment | Stores the relationship between Student and Course. |
| Payment | Stores fee payment details of students. |

---

### 5.3 Relationships

Relationships are used to connect objects with each other.

In my College Management System:

- One Student can enroll in one or more Courses.
- One Course can have many Students.
- One Faculty member can teach one or more Courses.
- One Student can have many Payment records.

Example:

Student ↔ Course

This means students and courses are connected through enrollment.

---

### 5.4 Validation

Validation rules are used to make sure correct data is entered.

Example validation rules in my College Management System:

1. Student email should be required.
2. Phone number should not be empty.
3. Course seats should not be negative.
4. Attendance percentage should not be more than 100.
5. Fee amount should not be less than 0.

Example:

If a student record is created without an email, the system should show an error message:

"Email is required for student registration."

---

### 5.5 Formula

Formula fields are used to calculate values automatically.

Example formula in my College Management System:

Remaining Seats = Total Seats - Enrolled Students

This helps the college know how many seats are still available in a course.

Other examples:

- Total Fee = Course Fee + Hostel Fee + Transport Fee
- Attendance Status = If attendance is less than 75%, show "Low Attendance"
- Payment Status = If paid amount equals total fee, show "Paid"

---

### 5.6 Flow

Flow is used to automate simple business processes without code.

Example Flow in my College Management System:

When a student successfully enrolls in a course, the system automatically sends a confirmation email to the student.

Another example:

When attendance is below 75%, send a notification to the student.

Flow is useful here because these are simple automation tasks that can be done using clicks.

---

### 5.7 Apex

Apex is used when the business logic becomes complex.

Example Apex use cases in my College Management System:

- Block registration if course seats are full.
- Calculate complex fee discounts based on scholarship and category.
- Connect Salesforce with an external payment gateway.
- Check advanced student eligibility before enrollment.
- Automatically update multiple related records after registration.

Apex adds more flexibility when Flow and configuration are not enough.

---

## 6. Complete System Explanation

My College Management System is designed to manage student admissions, courses, faculty, enrollments, attendance, and payments.

First, the admission process starts like a CRM pipeline. A student enquiry can be treated like a lead. When the student applies, the record moves through different stages like application submitted, admission review, course selected, and admission confirmed.

The system uses objects like Student, Course, Faculty, Enrollment, and Payment to store important data. Relationships connect these objects. For example, a student can enroll in a course, and a course can have many students.

Validation rules are used to keep the data correct. For example, student email is required, attendance should not be more than 100%, and available seats should not become negative.

Formula fields are used to calculate values automatically, such as remaining seats and payment status.

Flows are used for simple automation like sending confirmation emails and attendance notifications.

Apex is used for advanced business logic like checking seat availability, calculating complex fees, verifying eligibility, and integrating with payment systems.

This system shows how Salesforce uses both declarative tools and programming to build real enterprise applications.

---

## 7. Pseudocode Examples

### Pseudocode 1: Block Registration if Seats Are Full

IF remaining seats are equal to 0  
THEN block student registration  
SHOW message "Course seats are full"  
ELSE allow student registration  
UPDATE enrolled student count  

---

### Pseudocode 2: Notify Student if Attendance is Below 75%

IF student attendance is less than 75%  
THEN send notification to student  
MESSAGE "Your attendance is below the required percentage"  
ELSE no action needed  

---

### Pseudocode 3: Check Student Eligibility for Course

IF student marks are greater than or equal to minimum marks  
AND student fees are cleared  
AND course seats are available  
THEN allow course enrollment  
ELSE reject enrollment  
SHOW message "Student is not eligible for this course"  

---

### Pseudocode 4: Fee Discount Calculation

IF student has scholarship  
THEN apply scholarship discount  

IF student belongs to special category  
THEN apply category discount  

CALCULATE final fee  

DISPLAY final fee amount  

---

### Pseudocode 5: Payment Status Update

IF paid amount is equal to total fee  
THEN update payment status as "Paid"  

ELSE IF paid amount is greater than 0  
THEN update payment status as "Partially Paid"  

ELSE update payment status as "Not Paid"  

---

## 8. Reflection

### Why cannot all enterprise logic be built using only clicks and configuration?

All enterprise logic cannot be built using only clicks and configuration because real business requirements are often complex. Configuration tools are very useful for simple and standard processes, but they may not handle advanced calculations, multiple conditions, external integrations, and large-scale custom logic easily.

For example, in a College Management System, sending an email notification can be done using Flow. But checking eligibility, calculating fee discounts, blocking registration, updating related records, and connecting with a payment gateway may require custom Apex code.

Enterprise systems need flexibility, performance, security, and advanced logic. Apex helps developers build custom solutions when declarative tools are not enough.

---

## 9. Reflective Questions

### 1. Why is Apex needed if Salesforce already has Flows?

Apex is needed because Flows are useful for simple and medium-level automation, but some business problems require complex logic, advanced calculations, database operations, integrations, and custom error handling. Apex gives developers more control and flexibility.

---

### 2. When should developers prefer no-code solutions?

Developers should prefer no-code solutions when the requirement is simple, easy to maintain, and can be completed using Salesforce configuration tools like Flow, validation rules, formula fields, approval processes, and page layouts.

For example, sending an email when a student enrolls in a course can be done using Flow instead of Apex.

---

### 3. What problems require custom programming?

Custom programming is required for problems such as:

- Complex fee calculation
- Advanced eligibility checking
- External system integration
- Custom business rules
- Large data processing
- Complex approval logic
- Custom error handling
- Updating multiple related records with advanced logic

---

### 4. Why is business logic important in enterprise systems?

Business logic is important because it defines how an organization works. It ensures that the system follows real business rules correctly.

For example, in a College Management System, students should not be allowed to register if course seats are full. This rule is business logic.

Without business logic, the system may accept wrong data or allow incorrect actions.

---

### 5. Why should developers avoid unnecessary coding?

Developers should avoid unnecessary coding because code takes more time to write, test, debug, and maintain. If a requirement can be completed using clicks and configuration, it is better to use no-code tools.

Unnecessary coding can make the system complex and harder to manage.

A good developer should choose the simplest and most suitable solution.

---

### 6. How does programming increase flexibility?

Programming increases flexibility because developers can create custom logic based on exact business requirements. Apex allows developers to use conditions, loops, methods, classes, database queries, and integrations.

With programming, Salesforce can handle advanced scenarios that are difficult or impossible using only configuration.

For example, Apex can calculate student eligibility by checking marks, attendance, fee status, seat availability, and prerequisites together.

---

## 10. Learnings from Day 5

From Day 5, I learned that Apex is an important part of Salesforce development. Salesforce provides many declarative tools, but programming is needed when business logic becomes complex.

I also understood the difference between Flow and Apex. Flow is useful for automation using clicks, while Apex is useful for advanced logic using code.

I learned that a good Salesforce developer should not directly choose coding for every problem. First, they should check whether the requirement can be solved using configuration or Flow. Apex should be used only when no-code or low-code tools are not enough.

---

## 11. Doubts / Questions

- When should I choose Apex instead of Flow?
- How do Apex triggers work with objects?
- How can Apex connect Salesforce with external systems?
- How much Apex syntax is needed for real-time projects?
- How do we test Apex code before deploying?

---

## 12. Conclusion

Day 5 helped me understand why Apex exists in Salesforce. Apex is used to build custom business logic when normal clicks and flows are not enough.

In my College Management System, simple tasks like email notifications can be handled using Flow, while complex tasks like fee calculation, eligibility checking, seat blocking, and payment integration can be handled using Apex.

Overall, Apex makes Salesforce more powerful, flexible, and suitable for real enterprise applications.
