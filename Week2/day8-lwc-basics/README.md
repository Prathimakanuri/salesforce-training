# Day 8 - Lightning Web Components (LWC) Basics

## Notes from Today

Today I learned about Lightning Web Components (LWC), component-based UI architecture, frontend and backend separation, and why Salesforce uses reusable components to build modern enterprise applications.

Lightning Web Components are used in Salesforce to build fast, modern, reusable, and secure user interfaces. LWC helps developers create small UI parts called components, which can be reused in different screens of an application.

---

## What is LWC?

LWC stands for Lightning Web Components. It is a modern framework provided by Salesforce to build user interfaces using standard web technologies like HTML, JavaScript, and CSS.

In Salesforce, LWC is used to create interactive pages, forms, dashboards, tables, cards, buttons, and other UI elements. Each LWC component has its own structure and purpose.

A basic LWC component contains:

- HTML file for the user interface
- JavaScript file for logic and actions
- Meta XML file for component configuration
- CSS file if styling is needed

Example component structure:

studentDashboard/
- studentDashboard.html
- studentDashboard.js
- studentDashboard.js-meta.xml
- studentDashboard.css

LWC makes development easier because every feature can be divided into small reusable components.

---

## Why Salesforce Uses LWC

Salesforce uses LWC because modern enterprise systems need fast, reusable, secure, and scalable user interfaces.

Reasons why Salesforce uses LWC:

1. Modern Web Standards  
LWC uses standard HTML, JavaScript, and CSS, so it is easy for web developers to understand and use.

2. Reusable Components  
One component can be reused in many pages. For example, a notification component can be used in student dashboard, faculty dashboard, and admin dashboard.

3. Better Performance  
LWC is lightweight and faster compared to older UI frameworks.

4. Component-Based Development  
Large applications can be divided into small components, making development and maintenance easier.

5. Easy Maintenance  
If a change is needed, we can update one component instead of changing the entire application.

6. Secure UI Development  
LWC follows Salesforce security standards and helps developers build safer applications.

---

## College Management System - UI Screens / Components Needed

For my College Management System, the following UI screens/components are needed:

### 1. Student Registration Form

This screen is used to collect student details like name, email, phone number, department, year, address, and admission details. It helps the college store student information digitally.

### 2. Student Dashboard

This screen shows important details to students such as personal information, attendance percentage, enrolled courses, fee status, exam updates, and notifications.

### 3. Attendance View

This screen displays attendance details subject-wise. Students can check their present percentage, absent days, and overall attendance status.

### 4. Faculty Panel

This screen is used by faculty members to manage student attendance, upload marks, view student lists, and send updates.

### 5. Notifications Widget

This component shows important announcements such as exam dates, fee reminders, timetable updates, college events, and placement news.

---

## Component Thinking

### Selected Screen: Student Dashboard

I selected the Student Dashboard screen because it contains many small sections that can be divided into reusable components.

### Component Breakdown

The Student Dashboard can be divided into the following reusable components:

### 1. Header Component

This component displays the college name, student name, profile icon, and logout button.

This component can be reused in:

- Student Dashboard
- Faculty Dashboard
- Admin Dashboard

### 2. Student Info Component

This component displays student details like name, roll number, department, year, email, and phone number.

This component can be reused in:

- Student Profile Page
- Admin Student Details Page
- Faculty Student View Page

### 3. Attendance Component

This component shows attendance percentage, subject-wise attendance, and warning messages if attendance is low.

This component can be reused in:

- Student Dashboard
- Faculty Panel
- Parent View

### 4. Course Component

This component displays the subjects or courses registered by the student.

This component can be reused in:

- Student Dashboard
- Course Registration Page
- Faculty Course Page

### 5. Fee Status Component

This component shows whether the student has paid the college fee or if any amount is pending.

This component can be reused in:

- Student Dashboard
- Admin Fee Management Page

### 6. Notification Component

This component displays announcements, reminders, and important alerts.

This component can be reused in:

- Student Dashboard
- Faculty Dashboard
- Admin Dashboard

---

## Why Reusable Components Are Useful

Reusable components are useful because they save time and reduce repeated work. If the same UI part is needed in multiple places, we can create it once and use it again.

For example, the notification component can be used for students, faculty, and admin users. If we want to change the design of notifications, we only need to update the notification component once.

Reusable components are useful because:

- They reduce duplicate code
- They make the application easier to maintain
- They improve consistency in UI design
- They save development time
- They make debugging easier
- They support modular development

---

## Frontend vs Backend Logic

In an enterprise application, frontend and backend logic should be separated clearly.

The frontend is responsible for what the user sees and interacts with. The backend is responsible for business logic, database operations, security, and calculations.

| Feature / Logic | Frontend / UI | Backend / Apex |
|---|---|---|
| Button click | Yes | No |
| Showing student dashboard | Yes | No |
| Displaying notifications | Yes | Data comes from backend |
| Form input fields | Yes | No |
| Basic required field message | Yes | Can also be validated in backend |
| Saving student data | No | Yes |
| Fee calculation | No | Yes |
| Attendance percentage calculation | Can display result | Actual calculation should be in backend |
| Checking user permissions | No | Yes |
| Fetching records from database | No | Yes |
| Updating marks or attendance | No | Yes |
| Final data validation | No | Yes |

---

## Examples of Frontend and Backend Thinking

### 1. Button Click

When a student clicks the View Attendance button, the click action belongs to the frontend. The frontend sends a request to get attendance data.

### 2. Data Validation

Simple validation like checking whether a field is empty can happen in the frontend. But important validation must also happen in the backend to keep the system secure.

### 3. Fee Calculation

Fee calculation should happen in the backend because it is business logic. The frontend should only display the calculated fee amount.

### 4. Notification Display

The frontend displays notifications in a clean UI. But the notification data should come from the backend or database.

### 5. Attendance Calculation

The backend should calculate attendance percentage based on total classes and attended classes. The frontend should only display the final percentage to the student.

---

## Reflection

### Why do modern enterprise systems use component-based UI architecture?

Modern enterprise systems use component-based UI architecture because large applications are difficult to manage as one single block. By dividing the application into small components, development becomes easier, faster, and more organized.

Each component has a specific responsibility. For example, in a college management system, the attendance component only handles attendance display, the notification component only handles announcements, and the student info component only displays student details.

This approach makes the application more reusable and maintainable. If one component has an error, we can fix that component without disturbing the whole application. It also helps teams work better because different developers can work on different components at the same time.

Component-based UI is important because it improves performance, saves time, supports clean design, and helps build scalable enterprise applications.

---

## Revision Questions

### 1. What is a component?

A component is a small reusable part of a user interface. It performs a specific function in an application. For example, a header, form, button, attendance card, or notification box can be a component.

### 2. Why are reusable components useful?

Reusable components are useful because they reduce duplicate code and save development time. Once a component is created, it can be used in many screens. This makes the application easy to maintain and keeps the UI consistent.

### 3. Difference between frontend and backend?

Frontend is the part of the application that users see and interact with. It includes screens, buttons, forms, dashboards, and layout.

Backend is the part that handles data, business logic, security, database operations, and calculations.

Example:

Frontend: Student clicks a button to view attendance.  
Backend: System fetches attendance records and calculates percentage.

### 4. Why did Salesforce move toward LWC?

Salesforce moved toward LWC because it is faster, modern, lightweight, and based on standard web technologies. LWC provides better performance and makes it easier to build reusable and scalable user interfaces.

### 5. Why is UI important in enterprise systems?

UI is important because users interact with the system through the interface. A good UI helps users complete tasks easily and quickly. In enterprise systems, a clear UI reduces confusion, saves time, and improves productivity.

### 6. Why should systems separate UI and business logic?

Systems should separate UI and business logic because it makes the application cleaner, safer, and easier to maintain. UI should focus on displaying data and taking user input, while business logic should be handled in the backend.

This separation also improves security because important operations like fee calculation, database updates, and permission checks should not be handled only in the frontend.

### 7. What security risks exist in enterprise applications?

Some common security risks in enterprise applications are:

- Unauthorized access to data
- Weak user permissions
- Data leakage
- Incorrect access control
- Exposing sensitive information
- Poor validation of user input
- Insecure coding practices

To avoid these risks, developers should follow security best practices, validate data properly, and use correct profiles, permissions, and access controls.

### 8. Why should developers think modularly?

Developers should think modularly because modular development helps divide a large application into smaller parts. Each module or component can be developed, tested, reused, and maintained separately.

Modular thinking makes the application more organized, scalable, and easy to debug.

---

## Learnings

From Day 8, I learned:

- LWC means Lightning Web Components
- LWC is used to build modern Salesforce user interfaces
- Components are reusable UI parts
- Component-based architecture improves maintainability
- Frontend handles user interaction and display
- Backend handles business logic, database, and security
- Reusable components reduce duplicate code
- Enterprise systems need secure and scalable UI design

---

## Doubts / Questions

- How can LWC components communicate with each other?
- How can Apex be connected with LWC?
- How can we fetch Salesforce records inside an LWC component?
- How can we deploy LWC components in a Salesforce org?

---


## End of Day Outcome

By completing Day 8, I understood what Lightning Web Components are and why Salesforce uses modern component-based UI development. I also learned how to think about frontend and backend separation, reusable UI components, and secure enterprise application design.
