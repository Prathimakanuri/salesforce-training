# Salesforce Summer Program – Day 16  
## Debugging, Developer Tools & Best Practices

## Day 16 Overview

Day 16 focuses on understanding how Salesforce developers diagnose, debug, improve, and maintain enterprise-level systems.

The main goal of this day is to learn how real developers identify bugs, trace errors, improve performance, and write maintainable code.

Debugging is one of the most important skills in software engineering because enterprise applications are used by many users and even a small issue can affect business operations.

## Goal for Today

Today’s learning goal is:

How developers diagnose, debug, improve, and maintain enterprise systems.

The focus areas are:

- Debugging
- Developer tools
- Error analysis
- Performance thinking
- Lightning Web Components best practices
- Maintainable architecture
- Reliable enterprise systems

## Modules Completed

## 1. Find and Fix Bugs with Apex Replay Debugger

This module helped me understand how developers use Apex Replay Debugger to analyze Apex code execution step by step.

Key learning points:

- How to read debug logs
- How to trace errors
- How to identify the root cause of bugs
- How to use replay debugging in VS Code
- How debugging helps in fixing Apex issues efficiently

## 2. Developer Console Basics

This module introduced the important tools available in Salesforce Developer Console.

Key learning points:

- Using the Query Editor
- Viewing debug logs
- Executing Apex code
- Checking errors
- Understanding execution results
- Using Developer Console for troubleshooting

Developer Console is useful for quickly testing Apex, running SOQL queries, and checking logs without leaving Salesforce.

## 3. Best Practices in Lightning Web Components

This module explained how to write clean, reusable, and high-performance Lightning Web Components.

Key learning points:

- Writing clean component code
- Improving component performance
- Creating reusable components
- Maintaining proper file structure
- Avoiding unnecessary logic in UI components
- Using reusable architecture for long-term maintainability

## Videos Watched

## 1. Salesforce Apex: How to Read & Use Debug Logs for Troubleshooting

Link: https://www.youtube.com/watch?v=tPPv4VQY89k

Channel: Apex Hours

Focus areas:

- Debug logs
- Troubleshooting
- Error tracing
- Root cause analysis

## 2. Developer Console in Salesforce

Link: https://www.youtube.com/watch?v=2KRGa86nbOg

Channel: Salesforce Hulk

Focus areas:

- Developer Console basics
- Query Editor
- Executing Apex
- Debugging tools

## 3. LWC Best Practices

Link: https://www.youtube.com/watch?v=q3e0Qx2D6lY

Channel: Salesforce Developers

Focus areas:

- Clean components
- Performance optimization
- Reusable architecture

## 4. Salesforce Developer Tutorial – Apex Replay Debugger

Link: https://www.youtube.com/watch?v=iWXvnylWuR8

Channel: Coding With The Force

Focus areas:

- Replay Debugger
- VS Code debugging
- Apex troubleshooting
- Enterprise debugging workflow

## Core Task 1 – Bug Analysis

In enterprise systems, bugs can happen in many areas such as automation, Apex, flows, UI components, approval processes, and notifications.

A developer should not directly guess the solution. First, the issue should be understood clearly, then logs and records should be checked.

## Scenario 1: Duplicate Notifications Occur

## Problem

Users are receiving the same notification more than once.

## Possible Causes

- Same email alert is used in multiple flows
- Workflow rule and flow both send notifications
- Trigger and process automation are performing the same action
- Record is updated multiple times
- Notification logic is not checking whether the notification was already sent

## Debugging Approach

1. Identify when the duplicate notification is sent.
2. Check all flows, workflow rules, process builders, triggers, and approval actions related to the object.
3. Check debug logs for repeated execution.
4. Verify whether the record is updated multiple times.
5. Check if the automation has proper conditions.
6. Add a condition field such as Notification_Sent__c to avoid repeated notifications.
7. Test the notification process using sample records.

## Solution

Use clear entry conditions and avoid creating multiple automations for the same action.

A flag field can be used to track whether the notification has already been sent.

## Scenario 2: Attendance Calculations Are Wrong

## Problem

Attendance percentage or attendance count is calculated incorrectly.

## Possible Causes

- Wrong formula field
- Incorrect Apex calculation logic
- Missing records
- Duplicate attendance entries
- Incorrect date filtering
- Roll-up summary not updated properly
- Flow updating wrong fields

## Debugging Approach

1. Check sample student attendance records manually.
2. Compare manual calculation with system calculation.
3. Verify the formula or Apex logic.
4. Check whether duplicate attendance records exist.
5. Check SOQL queries used for fetching attendance data.
6. Check debug logs to understand actual values used in calculation.
7. Test different cases such as absent, present, late, and holiday records.

## Solution

The calculation logic should be simple, accurate, and tested with different data cases.

Validation rules can be added to avoid duplicate attendance records.

## Scenario 3: Flow Not Triggering

## Problem

A record-triggered flow is not running when expected.

## Possible Causes

- Flow is inactive
- Wrong object selected
- Entry conditions are incorrect
- Flow is triggered only on create but record is being updated
- User does not have required permissions
- Record does not meet criteria
- Flow order conflicts with other automation

## Debugging Approach

1. Check whether the flow is active.
2. Verify the flow object.
3. Check the trigger condition: created, updated, or created/updated.
4. Test with a record that clearly satisfies the condition.
5. Use the Debug option in Flow Builder.
6. Check Setup → Paused and Failed Flow Interviews.
7. Review debug logs for flow execution details.
8. Check field-level security and user permissions.

## Solution

Correct the flow trigger conditions and activate the flow.

Use Flow Debug before testing on real data.

## Scenario 4: Approval Process Stuck

## Problem

A record is submitted for approval but it is not moving to the next step.

## Possible Causes

- Approver is missing
- Approval criteria are not met
- Record is locked
- Approval step condition is wrong
- User does not have permission
- Email notification is not delivered
- Final approval or rejection actions are not configured properly

## Debugging Approach

1. Check the approval history on the record.
2. Verify the current approval step.
3. Check whether the assigned approver is correct.
4. Review approval criteria.
5. Check if the record is locked.
6. Verify initial submission actions and final actions.
7. Check whether the approver has permission to approve.
8. Test approval process using a sample record.

## Solution

Approval steps should have clear conditions and correct approver assignments.

Approval history should be checked to understand where the process is stuck.

## Core Task 2 – Performance Thinking

## Scenario

Suppose 50,000 users use the system simultaneously.

When many users use a system at the same time, performance problems can occur in different layers of the application.

## UI Problems

Possible UI issues:

- Pages may load slowly
- Components may take more time to render
- Too many records displayed at once can freeze the page
- Large images or heavy scripts can reduce performance
- Repeated server calls can make the UI slow
- Poorly designed Lightning Web Components can affect user experience

## UI Solutions

- Use pagination
- Use lazy loading
- Avoid loading unnecessary data
- Keep LWC components lightweight
- Use reusable components
- Reduce unnecessary Apex calls
- Display only required fields

## Backend Problems

Possible backend issues:

- Apex code may hit governor limits
- Too many SOQL queries can fail execution
- Too many DML operations can slow down processing
- Poorly written triggers may execute repeatedly
- Large transactions may fail
- Synchronous processing may become slow

## Backend Solutions

- Bulkify Apex code
- Avoid SOQL inside loops
- Use asynchronous Apex when needed
- Use Queueable Apex, Batch Apex, or Future methods
- Optimize trigger logic
- Handle exceptions properly

## Database Problems

Possible database issues:

- Queries may become slow
- Large data volume can affect performance
- Non-selective SOQL queries may fail
- Duplicate records may increase storage and confusion
- Reports may load slowly
- Data locking can occur when many users update the same records

## Database Solutions

- Use selective SOQL queries
- Add proper filters
- Avoid fetching unnecessary fields
- Use indexes where applicable
- Archive old data
- Avoid duplicate records
- Design proper data relationships

## Notification Problems

Possible notification issues:

- Duplicate notifications may be sent
- Email limits may be reached
- Users may receive delayed notifications
- Push notifications may fail
- Too many alerts may confuse users

## Notification Solutions

- Use proper notification conditions
- Avoid duplicate automation
- Track sent notifications
- Use scheduled notifications where required
- Group notifications when possible

## Automation Problems

Possible automation issues:

- Flows may run slowly
- Multiple automations may conflict
- Record updates may trigger other automations repeatedly
- Approval processes may get delayed
- System may hit automation limits

## Automation Solutions

- Use one automation per business process where possible
- Avoid unnecessary record updates
- Keep flow logic simple
- Test automation with bulk records
- Monitor failed flow interviews
- Use clear entry and exit conditions

## Core Task 3 – Maintainability Thinking

## Why Developers Should Write Modular Code

Modular code means dividing a large program into smaller, meaningful parts.

Benefits:

- Easy to understand
- Easy to test
- Easy to debug
- Easy to reuse
- Easy to update
- Reduces complexity

In Salesforce, modular code helps developers manage Apex classes, triggers, flows, and LWC components in a clean way.

## Why Developers Should Write Reusable Components

Reusable components can be used in multiple places without rewriting the same logic again.

Benefits:

- Saves development time
- Reduces duplicate code
- Improves consistency
- Makes updates easier
- Helps teams work faster

For example, a reusable LWC button, card, or table component can be used in many pages.

## Why Developers Should Build Debuggable Systems

A debuggable system is easy to inspect, test, and troubleshoot.

Benefits:

- Bugs can be found faster
- Errors can be traced easily
- System behavior becomes clear
- Production issues can be solved quickly
- Maintenance becomes easier

Debuggable systems should include proper logs, meaningful error messages, clean code, and clear separation of logic.

## Why Quick Hacks Should Be Avoided

Quick hacks may solve the problem temporarily, but they create long-term issues.

Problems with quick hacks:

- Code becomes difficult to understand
- Bugs become harder to fix
- Future changes become risky
- Performance may become poor
- Duplicate logic increases
- Team collaboration becomes difficult

A good developer should focus on long-term quality, not only short-term completion.

## Lightning Web Components Best Practices

Lightning Web Components should be designed carefully because they directly affect the user experience.

## 1. Keep Components Small

Each component should do one clear task.

Large components are difficult to understand and maintain.

## 2. Use Reusable Components

Common UI parts such as cards, buttons, tables, and forms should be reusable.

## 3. Avoid Unnecessary Apex Calls

Calling Apex repeatedly can slow down the application.

Data should be fetched only when required.

## 4. Use Proper Naming

Files, variables, methods, and components should have meaningful names.

Examples:

- studentAttendanceList
- calculateAttendancePercentage
- handleSave

## 5. Separate Business Logic

Business logic should not be mixed too much with UI logic.

Complex logic should be handled in Apex or helper methods.

## 6. Handle Errors Properly

Users should see clear error messages instead of technical errors.

Example error message:

Unable to save record. Please try again.

## 7. Optimize Performance

Components should load only necessary data.

Avoid rendering large data sets at once.

## 8. Follow Clean Architecture

A good LWC project should have:

- Clear component structure
- Reusable components
- Proper communication between parent and child components
- Clean JavaScript logic
- Simple HTML templates
- Minimal CSS duplication

## Enterprise Debugging Workflow

A professional debugging workflow includes the following steps:

## Step 1: Understand the Problem

First, clearly understand what is not working.

Questions to ask:

- What is the expected result?
- What is the actual result?
- When does the issue occur?
- Which users are affected?
- Is the issue happening always or sometimes?

## Step 2: Reproduce the Issue

Try to recreate the same issue in a test environment.

This helps confirm the exact problem.

## Step 3: Check Logs

Use debug logs to understand what happened internally.

Logs help identify:

- Apex execution
- Flow execution
- SOQL queries
- DML operations
- Errors
- Governor limit issues

## Step 4: Identify Root Cause

Do not fix only the visible symptom.

Find the actual reason behind the issue.

Example:

If duplicate emails are sent, the root cause may be duplicate automation, not the email alert itself.

## Step 5: Fix the Issue

Apply the correct solution based on the root cause.

The fix should be clean and maintainable.

## Step 6: Test the Fix

Test the fix with different cases.

Examples:

- Normal case
- Error case
- Bulk data case
- Permission-based case

## Step 7: Document the Solution

Write what the issue was, why it happened, and how it was fixed.

Documentation helps future developers understand the system.

## Reflection

## Why Debugging Is One of the Most Important Skills in Software Engineering

Debugging is important because no software system is perfect. Bugs can happen due to wrong logic, wrong data, user mistakes, automation conflicts, or system limits.

In enterprise systems like Salesforce, debugging is even more important because many users depend on the system for daily business work. If a bug is not fixed properly, it can affect users, business processes, reports, approvals, notifications, and customer experience.

Debugging helps developers understand how the system actually works. It also improves problem-solving skills. A good developer should not only write code but also understand how to find and fix issues when something goes wrong.

Debugging teaches patience, logical thinking, and root cause analysis. It helps developers build reliable and maintainable systems.

## Revision Questions and Answers

## 1. Why are debug logs important?

Debug logs are important because they show what happens inside the system during execution.

They help developers trace Apex code, flows, SOQL queries, DML operations, errors, and governor limits.

## 2. Why is debugging difficult in enterprise systems?

Debugging is difficult in enterprise systems because many components work together.

A single issue may involve Apex, flows, triggers, validation rules, approval processes, permissions, and integrations.

## 3. What problems happen when systems scale?

When systems scale, problems like slow UI, database performance issues, governor limit errors, duplicate notifications, automation conflicts, and data locking can happen.

## 4. Why should components be reusable?

Reusable components reduce duplicate code and save development time.

They also improve consistency and make future changes easier.

## 5. Why is maintainability important?

Maintainability is important because software needs updates, bug fixes, and improvements over time.

A maintainable system is easier to understand, modify, test, and debug.

## 6. Why should developers avoid tightly coupled code?

Tightly coupled code is difficult to change because one part of the system depends too much on another part.

Changing one component may break other components.

Loosely coupled code is easier to maintain and test.

## 7. Why do enterprise systems require monitoring?

Enterprise systems require monitoring to detect failures, performance issues, errors, and unusual behavior early.

Monitoring helps developers fix issues before they affect many users.

## 8. Why is troubleshooting an important engineering skill?

Troubleshooting is important because developers must identify and solve real-world problems.

It helps in finding root causes, fixing issues, improving system reliability, and supporting users effectively.

## GitHub Submission

Create the following folder in the GitHub repository:

/day16-debugging-best-practices/

Inside this folder, create:

README.md

The README should include:

- Common bug scenarios
- Debugging approach
- Performance discussion
- LWC best practices
- Reflection
- Revision questions and answers

## End of Day Outcome

After completing Day 16, I understood:

- Enterprise debugging workflow
- How to use Developer Console
- Importance of debug logs
- Apex Replay Debugger basics
- Common bug analysis methods
- Performance issues in large-scale systems
- Lightning Web Components best practices
- Importance of maintainable architecture
- Reliability and troubleshooting thinking

## Conclusion

Day 16 helped me understand that debugging is not only about fixing errors.

It is about understanding the system deeply, identifying the root cause, improving performance, and writing maintainable solutions.

A good Salesforce developer should build systems that are reliable, scalable, reusable, and easy to debug.
