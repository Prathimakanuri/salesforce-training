# Salesforce Summer Program – Day 14
## Flow Governance and Enterprise Workflow Design

---

## Goal of the Day

The goal of Day 14 is to understand how Salesforce automation moves from simple automation to controlled enterprise workflows.

Today’s focus is on learning Salesforce Flow Builder logic, decision-based automation, variables, branching, approval workflows, governance, and controlled enterprise processes.

By completing this task, I understood how real organizations use Salesforce to control important business operations safely, accurately, and systematically.

---

## Modules Completed

## 1. Flow Builder Logic

Flow Builder is a Salesforce automation tool used to create workflows without writing much code. It helps automate business processes using logic, conditions, variables, formulas, and actions.

### Key Concepts Learned

- Decision elements
- Branching paths
- Variables
- Formula logic
- Multi-step workflows
- Business process automation

Flow Builder allows users to create smart automation. Instead of performing the same task manually again and again, we can create a flow that automatically performs actions based on given conditions.

For example, in a college system, if a student’s attendance is low, the system can automatically send a warning email, notify parents, or escalate the issue to the admin based on attendance percentage.

---

## 2. Approve Records with Approval Processes

Approval processes in Salesforce are used to control important actions. They ensure that sensitive records are reviewed by the correct people before final approval.

### Key Concepts Learned

- Approval workflows
- Multi-level approvals
- Enterprise governance
- Controlled business operations
- Approval and rejection actions

Approval processes are useful in large organizations because every important action cannot be directly performed by one person. Some actions need proper checking, approval, and tracking.

For example, a budget request in a college should not be approved directly. It should first be checked by the Head of Department, then by the Finance Department, and finally by the Principal or Director.

---

## Videos Referred

## 1. Introduction to Salesforce Flow Builder | Day 1

Link: https://www.youtube.com/watch?v=og6WyT2Ry-Y

Channel: Apex Hours

Focus:

- Flow Builder basics
- Flow structure
- Resources and logic

---

## 2. Salesforce Flow Crash Course

Link: https://www.youtube.com/watch?v=KVs_omNlaxg

Channel: Apex Hours

Focus:

- Salesforce Flow overview
- Automation concepts
- Beginner-friendly flow understanding

---

## 3. Building Advanced Flows with Choices, Loops, and Apex

Link: https://www.youtube.com/watch?v=Tr3GG-aLU4Q

Channel: Apex Hours

Focus:

- Advanced flow logic
- Choices and loops
- Multi-step automation
- Invocable Apex

---

# Core Task 1: Multi-Level Approval Design

## College Management System – Approval Workflows

For this task, I designed approval workflows for a College Management System. These workflows are useful for controlling important actions such as course creation, faculty leave requests, student scholarship requests, and budget approval.

Approval workflows help ensure that important decisions are reviewed by the correct people in the correct order.

---

## 1. Course Creation Approval Workflow

### Scenario

In a college, a new course may be proposed by a faculty member or department. Before the course is added to the official academic system, it must be reviewed and approved by multiple authorities.

### Approval Order

| Step | Approver | Responsibility |
|---|---|---|
| 1 | Faculty / Course Coordinator | Creates the course request |
| 2 | Head of Department | Checks department need and course relevance |
| 3 | Academic Dean | Reviews academic quality, syllabus, and credits |
| 4 | Principal / Director | Gives final approval |

### Workflow Explanation

The faculty member first creates a new course request with details such as course name, course code, syllabus, credits, department, prerequisites, and learning outcomes.

After submission, the request goes to the Head of Department. The HOD checks whether the course is useful for the department and whether it matches the academic goals.

If the HOD approves the request, it moves to the Academic Dean. The Academic Dean reviews the syllabus, course structure, credits, academic standards, and student benefits.

After academic review, the request goes to the Principal or Director for final approval. Once approved, the course becomes active in the college system.

### After Approval

- Course status changes to Approved.
- Course is added to the official course list.
- Faculty and department receive notification.
- Students can view or register for the course.
- Course record is saved for future reference.

### After Rejection

- Course status changes to Rejected.
- Faculty receives rejection reason.
- Faculty can modify the course details.
- Request can be resubmitted if required.

---

## 2. Faculty Leave Request Approval Workflow

### Scenario

A faculty member applies for leave. Since faculty absence can affect classes, timetable, and students, the leave request must be approved properly.

### Approval Order

| Step | Approver | Responsibility |
|---|---|---|
| 1 | Faculty Member | Submits leave request |
| 2 | Head of Department | Checks class schedule and availability |
| 3 | Principal / Admin Office | Gives final leave approval |

### Workflow Explanation

The faculty member submits a leave request by entering leave dates, reason, and type of leave.

The request first goes to the Head of Department. The HOD checks whether the faculty member has classes, lab sessions, exams, or other responsibilities during the requested leave period.

If the leave does not create any major issue, or if alternate faculty can be arranged, the HOD approves it.

After HOD approval, the request goes to the Principal or Admin Office for final approval. The final authority checks whether the leave follows college rules and then approves or rejects it.

### After Approval

- Leave status changes to Approved.
- Faculty receives confirmation.
- Attendance or HR record is updated.
- Timetable changes may be updated.
- Alternate faculty may be assigned if needed.

### After Rejection

- Leave status changes to Rejected.
- Faculty receives the rejection reason.
- Faculty may apply again with updated details.
- Classes continue as scheduled.

---

## 3. Student Scholarship Request Approval Workflow

### Scenario

A student applies for a scholarship. Since scholarships involve financial support and eligibility verification, the request must go through multiple levels of approval.

### Approval Order

| Step | Approver | Responsibility |
|---|---|---|
| 1 | Student | Submits scholarship request |
| 2 | Class Teacher / Mentor | Verifies student details |
| 3 | Scholarship Committee | Checks eligibility and documents |
| 4 | Accounts Department | Verifies financial details and fund availability |
| 5 | Principal | Gives final approval |

### Workflow Explanation

The student submits a scholarship request with details such as academic marks, income certificate, category certificate, attendance, and other required documents.

The request first goes to the Class Teacher or Mentor. The mentor verifies whether the student details are correct.

After mentor verification, the request goes to the Scholarship Committee. The committee checks eligibility criteria, academic performance, documents, and rules.

If the student is eligible, the request moves to the Accounts Department. The accounts team verifies fund availability and financial details.

Finally, the request goes to the Principal for final approval.

### After Approval

- Scholarship status changes to Approved.
- Student receives approval notification.
- Accounts department processes the scholarship amount.
- Scholarship record is stored for audit.
- Student can track scholarship status.

### After Rejection

- Scholarship status changes to Rejected.
- Student receives rejection reason.
- Student may correct documents and resubmit if allowed.
- Request history is stored in the system.

---

## 4. Budget Approval Workflow

### Scenario

A department may request budget for seminars, workshops, lab equipment, cultural events, technical events, or academic activities. Since budget involves money, proper approval is required.

### Approval Order

| Step | Approver | Responsibility |
|---|---|---|
| 1 | Faculty / Event Coordinator | Creates budget request |
| 2 | Head of Department | Checks purpose and department need |
| 3 | Finance Department | Checks fund availability |
| 4 | Principal / Director | Gives final approval |

### Workflow Explanation

A faculty member or coordinator submits a budget request with details such as purpose, amount, event name, department, expected outcome, and required resources.

The request first goes to the Head of Department. The HOD checks whether the budget request is necessary and useful for the department.

If the HOD approves, the request goes to the Finance Department. The finance team checks whether funds are available and whether the requested amount is reasonable.

After finance verification, the request goes to the Principal or Director for final approval.

### After Approval

- Budget status changes to Approved.
- Finance team processes the budget.
- Department receives permission to use the amount.
- Budget record is saved for audit and tracking.
- Event or purchase can proceed.

### After Rejection

- Budget status changes to Rejected.
- Department receives rejection reason.
- Request may be modified and resubmitted.
- No amount is released.

---

# Core Task 2: Branching Flow Logic

## Branching Flow Example: Student Attendance Monitoring System

### Flow Name

Student Attendance Alert Flow

### Scenario

In a College Management System, student attendance is monitored regularly. Based on the attendance percentage, the system should automatically take different actions.

If attendance is slightly low, a warning email should be sent. If attendance is very low, parents should be notified. If attendance is critically low, the case should be escalated to the admin office.

---

## Flow Objective

The objective of this flow is to automatically monitor student attendance and trigger the correct action based on attendance percentage.

---

## Flow Logic

| Attendance Percentage | Decision Condition | Action Triggered |
|---|---|---|
| Attendance less than 75% | Attendance < 75% | Warning email to student |
| Attendance less than 60% | Attendance < 60% | Parent notification |
| Attendance less than 50% | Attendance < 50% | Admin escalation |
| Attendance 75% or above | Attendance >= 75% | No action required |

---

## Step-by-Step Flow Explanation

### Step 1: Start

The flow starts when a student attendance record is created or updated.

### Step 2: Get Attendance Record

The flow gets the student attendance percentage from the attendance record.

### Step 3: Decision Element

The flow uses a Decision element to check the attendance percentage.

### Step 4: Branching

Based on the attendance percentage, the flow moves into different branches.

---

## Decision Points and Branches

## Branch 1: Attendance Below 75%

### Condition

If attendance is less than 75%.

### Action Triggered

- Send warning email to student.
- Notify student to attend classes regularly.
- Update attendance status as Warning.

### Example Message

Your attendance is below 75%. Please attend classes regularly to avoid academic issues.

---

## Branch 2: Attendance Below 60%

### Condition

If attendance is less than 60%.

### Action Triggered

- Send notification to parents.
- Inform class teacher or mentor.
- Update attendance status as Serious Warning.

### Example Message

Your child’s attendance is below 60%. Please contact the college mentor for further discussion.

---

## Branch 3: Attendance Below 50%

### Condition

If attendance is less than 50%.

### Action Triggered

- Escalate the issue to the admin office.
- Notify HOD and mentor.
- Mark student as high-risk.
- Student may be called for counseling.

### Example Message

Student attendance is critically low. Admin attention is required immediately.

---

## Branch 4: Attendance 75% or Above

### Condition

If attendance is 75% or above.

### Action Triggered

- No warning needed.
- Attendance status remains Normal.
- No escalation required.

---

## Flow Structure

Start  
↓  
Get Student Attendance Record  
↓  
Decision: Check Attendance Percentage  
↓  
If Attendance < 50% → Admin Escalation  
Else If Attendance < 60% → Parent Notification  
Else If Attendance < 75% → Warning Email  
Else → No Action Required  

---

## Actions Triggered

| Branch | Action |
|---|---|
| Attendance < 50% | Admin escalation |
| Attendance < 60% | Parent notification |
| Attendance < 75% | Warning email to student |
| Attendance >= 75% | No action required |

---

## Importance of Branching Flow Logic

Branching flow logic is important because not every situation needs the same action.

For example, a student with 74% attendance only needs a warning email, but a student with 45% attendance needs admin escalation.

Branching workflows make automation more intelligent because they allow the system to choose the correct path based on business conditions.

---

# Core Task 3: Governance Thinking

## Why can’t enterprise systems allow everyone to directly change important records?

Enterprise systems cannot allow everyone to directly change important records because important records must be protected from unauthorized access, mistakes, misuse, wrong approvals, and business risks.

In a large organization, many users work with the same system. If every user can directly edit important records, it can create serious problems such as incorrect data, financial loss, security issues, and lack of accountability.

For example, in a college system, records such as student marks, scholarship approvals, budget approvals, course approvals, and faculty leave approvals are sensitive. These records should only be changed by authorized people after proper review.

---

## Reasons Why Direct Changes Should Be Restricted

## 1. Security

Important records may contain sensitive information. If everyone can edit them, confidential data may be misused or changed without permission.

Examples:

- Student scholarship details
- Faculty leave records
- Budget records
- Student marks
- Course approval details

---

## 2. Misuse Prevention

Some users may intentionally or accidentally misuse the system. For example, a scholarship amount should not be changed by any random user.

Only authorized users should be allowed to approve or update important records.

---

## 3. Avoiding Wrong Approvals

Important approvals need proper checking. A budget request should not be approved without checking fund availability.

Approval workflows ensure that the correct person reviews the request at the correct stage.

---

## 4. Business Risk Reduction

Wrong changes in enterprise systems can create financial, academic, legal, or operational risks.

Examples:

- Wrong scholarship approval may cause financial loss.
- Wrong course approval may affect academic quality.
- Wrong leave approval may disturb class schedules.
- Wrong budget approval may waste college funds.

---

## 5. Accountability

Controlled workflows help track who submitted, approved, rejected, or modified a record.

This creates responsibility and makes it easier to identify mistakes.

---

## 6. Audit and Compliance

Enterprises need proper records for future review. Approval workflows create a history of actions, approvals, rejections, and comments.

This helps during audits, reviews, and compliance checks.

---

## 7. Data Accuracy

If many people directly change important records, the data may become incorrect or inconsistent.

Controlled workflows help maintain accurate and reliable data.

---

# Core Task 4: Reflection

## Why do enterprises require controlled workflows instead of unrestricted actions?

Enterprises require controlled workflows because important business processes must follow rules, approval steps, and responsibilities.

If actions are unrestricted, users may make wrong changes, skip important checks, approve records without authority, or misuse sensitive information.

Controlled workflows help organizations maintain security, accuracy, accountability, and consistency. They make sure that every important action goes through the correct approval process.

For example, in a college system, a scholarship request should not be approved directly by one person. It should first be checked by the mentor, then by the scholarship committee, then by the accounts department, and finally by the principal.

Controlled workflows also reduce human errors because they guide users step by step. They make sure that correct actions happen based on business rules.

In simple words, controlled workflows protect an organization from mistakes, misuse, and business risk. They help enterprises work in a structured, safe, and professional way.

---

# Revision Questions

## 1. Why are approval workflows important?

Approval workflows are important because they ensure that important records and requests are reviewed by the correct people before final approval.

They help prevent unauthorized actions, mistakes, misuse, and wrong decisions.

For example, a scholarship request should be checked by the mentor, scholarship committee, accounts department, and principal before approval.

---

## 2. Why do businesses require governance?

Businesses require governance to control how decisions are made, who can access data, who can approve important records, and how business rules are followed.

Governance helps maintain security, accountability, compliance, and proper business control.

Without governance, users may make wrong changes or approve records without permission.

---

## 3. What are branching workflows?

Branching workflows are workflows that follow different paths based on conditions.

They use decision points to decide what action should happen next.

For example, if attendance is below 75%, a warning email is sent. If attendance is below 60%, parents are notified. If attendance is below 50%, the issue is escalated to admin.

---

## 4. Why should automation follow business rules?

Automation should follow business rules because every organization has specific policies, approval steps, and conditions.

If automation does not follow business rules, it may perform wrong actions.

For example, a budget request should be approved only after HOD review and finance verification. Automation must follow this rule to avoid financial risk.

---

## 5. Why are decision nodes important in flows?

Decision nodes are important because they allow a flow to choose different paths based on conditions.

They make automation smart, flexible, and useful.

For example, a decision node can check attendance percentage and decide whether to send a warning email, parent notification, or admin escalation.

---

## 6. Why should enterprises restrict sensitive operations?

Enterprises should restrict sensitive operations to protect important data and avoid unauthorized changes.

Sensitive operations may include approving budgets, changing marks, approving scholarships, updating salary details, or modifying employee records.

Only authorized users should perform these actions.

---

## 7. Why are approvals important in large organizations?

Approvals are important in large organizations because many people are involved in business operations.

Approval processes ensure that important decisions are reviewed properly and responsibility is clearly assigned.

They also help maintain trust, accuracy, security, and accountability.

---

## 8. Why should workflows be auditable?

Workflows should be auditable because organizations need to track who performed each action, when it was done, and why it was approved or rejected.

Audit history helps during reviews, investigations, compliance checks, and future decision-making.

For example, if a scholarship was approved, the college should be able to see who approved it, when it was approved, and what comments were given.

---

# Enterprise Workflow Thinking

Enterprise workflow thinking means designing processes that are not only automated but also controlled, secure, and aligned with business rules.

A good enterprise workflow should:

- Have clear approval steps
- Follow business rules
- Restrict unauthorized access
- Maintain audit history
- Reduce manual errors
- Trigger correct actions
- Support accountability
- Protect sensitive records
- Allow proper review before final decision

---

# GitHub Submission Structure

The GitHub repository should contain the following folder structure:

day14-flow-governance/
README.md

The README.md file should include:

- Approval workflow examples
- Branching flow logic
- Governance explanation
- Reflection
- Revision question answers

---

# End of Day Outcome

After completing Day 14, I clearly understood the importance of controlled enterprise workflows in Salesforce.

## I learned about:

- Approval workflows
- Branching automation logic
- Governance and enterprise control
- Multi-step business processes
- Structured workflow design
- Decision-based automation
- Flow Builder logic
- Enterprise-level approval processes
- Why sensitive operations should be restricted
- Why workflows should be auditable

---

# Conclusion

Day 14 helped me understand how Salesforce is used in real enterprise environments to automate and control business processes.

I learned that automation is not only about doing tasks faster, but also about doing them correctly, securely, and according to business rules.

Approval workflows and branching flows help organizations maintain control, reduce risk, improve decision-making, and protect important records.

Governance ensures that sensitive operations are handled only by authorized users and that every important action is properly tracked.

Overall, this task improved my understanding of Salesforce Flow governance, approval processes, branching automation, and enterprise workflow design.
