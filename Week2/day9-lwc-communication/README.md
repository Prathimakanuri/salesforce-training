# Salesforce Summer Program – Day 9  
## Lightning Web Components Communication and Application Architecture

## 📌 Day 9 Overview

Day 9 focused on understanding how Lightning Web Components communicate with each other, how data flows inside Salesforce applications, and why modern enterprise applications need modular architecture. The main topics covered today were component communication, parent-child data sharing, event-driven UI behavior, dashboard architecture, data flow thinking, Aura vs LWC comparison, and modular enterprise system design.

By the end of this day, I understood how different components inside an application interact with each other, how user actions move from the UI to the backend, and why Salesforce uses Lightning Web Components for building fast, reusable, and scalable applications.

---

## 🎯 Goal for Today

The goal of Day 9 was to understand:

- How components communicate with each other
- Data flow inside applications
- Event-driven UI behavior
- Parent-child communication
- Dynamic application architecture
- Why modular architecture is important in enterprise applications
- Why Salesforce moved from Visualforce and Aura Components to Lightning Web Components

---

## 📚 Deep Learning Modules

### 1. Lightning Web Components and Salesforce Data

This module helped me understand how Lightning Web Components connect with Salesforce data. LWC components can retrieve, display, and update data from Salesforce. They are reactive, meaning the UI can automatically update when data changes.

Important points learned:

- LWC helps connect frontend UI with Salesforce backend data.
- Components can display records, forms, lists, and dashboards.
- Data can be fetched using Apex or Lightning Data Service.
- Reactive properties help update the UI automatically.
- User interaction plays an important role in making applications dynamic.

Example:

If a student dashboard shows attendance percentage, the data may come from Salesforce records. When attendance is updated, the dashboard can automatically show the latest value.

---

### 2. Communicate Between Lightning Web Components

This module focused on how one Lightning Web Component communicates with another component.

Components communicate because large applications are divided into smaller reusable parts. One component may collect data, another may display data, and another may perform actions. Communication helps these components work together like one complete application.

Main communication methods:

- Parent to child communication
- Child to parent communication
- Events
- Data passing using properties
- Component interaction through user actions

Example:

In a student dashboard, the parent component may contain student details, attendance summary, and course information components. The parent sends student data to child components, and child components can send events back when the user performs an action.

---

## 🧩 Component Communication

Component communication means sharing data or messages between different components in an application.

In LWC, components are usually designed as small independent units. Each component has its own responsibility. But in a real application, components must communicate to complete a process.

### Why Components Communicate

Components communicate because:

- One component may need data from another component.
- User actions in one component may affect another component.
- Applications become easier to manage when features are divided into smaller parts.
- Reusable components reduce duplicate code.
- Communication helps create dynamic and interactive user interfaces.

Example:

If a student selects a course in one component, another component should display the faculty details or course schedule. This happens through component communication.

---

## 🔁 Types of Component Communication

### 1. Parent to Child Communication

Parent to child communication happens when a parent component passes data to a child component.

Example:

A Student Dashboard parent component can pass student name, roll number, attendance percentage, and enrolled courses to child components.

Flow:

Parent Component → Sends Data → Child Component

Example situation:

The main dashboard component has complete student information. It sends only attendance data to the attendance component and course data to the course component.

### 2. Child to Parent Communication

Child to parent communication happens when a child component sends information back to the parent component.

This is usually done using custom events.

Example:

A child component has a button called "Update Attendance". When the user clicks it, the child component sends an event to the parent component. The parent receives the event and updates the dashboard.

Flow:

Child Component → Fires Event → Parent Component Handles Event

### 3. Event-Based Communication

Event-based communication is used when a component needs to notify another component that something has happened.

Example:

When a student submits a registration form, an event can notify the parent component that registration is completed successfully.

Events are useful because they make the application interactive and dynamic.

---

## 🖥️ Dashboard Design

For this task, I designed three dashboards:

1. Student Dashboard
2. Faculty Dashboard
3. Admin Dashboard

Each dashboard contains different components based on the role of the user.

---

## 👨‍🎓 Student Dashboard

The Student Dashboard is designed for students to view their personal academic details.

### Components in Student Dashboard

- Student Profile Component
- Attendance Summary Component
- Course List Component
- Assignment Status Component
- Notification Component
- Registration Component

### Purpose of Each Component

#### Student Profile Component

Displays student details such as:

- Student name
- Roll number
- Department
- Year
- Email

#### Attendance Summary Component

Displays:

- Total classes
- Classes attended
- Attendance percentage
- Attendance status

#### Course List Component

Displays:

- Enrolled courses
- Course name
- Faculty name
- Course credits

#### Assignment Status Component

Displays:

- Pending assignments
- Submitted assignments
- Due dates
- Marks or feedback

#### Notification Component

Displays:

- Important announcements
- Registration confirmation
- Attendance alerts
- Assignment reminders

#### Registration Component

Allows students to register for courses or update required details.

---

## 👩‍🏫 Faculty Dashboard

The Faculty Dashboard is designed for faculty members to manage students and academic activities.

### Components in Faculty Dashboard

- Faculty Profile Component
- Course Management Component
- Student List Component
- Attendance Update Component
- Assignment Review Component
- Notification Component

### Purpose of Each Component

#### Faculty Profile Component

Displays faculty details such as:

- Faculty name
- Department
- Subject handled
- Email

#### Course Management Component

Helps faculty view and manage assigned courses.

#### Student List Component

Displays students enrolled in a particular course.

#### Attendance Update Component

Allows faculty to update student attendance.

#### Assignment Review Component

Allows faculty to check submitted assignments and provide feedback.

#### Notification Component

Helps faculty send announcements to students.

---

## 🛠️ Admin Dashboard

The Admin Dashboard is designed for administrators to manage the complete system.

### Components in Admin Dashboard

- Admin Profile Component
- Student Management Component
- Faculty Management Component
- Course Allocation Component
- Reports Component
- System Notification Component

### Purpose of Each Component

#### Admin Profile Component

Displays admin information and access details.

#### Student Management Component

Allows admin to:

- Add students
- Update student details
- Remove inactive records
- View student information

#### Faculty Management Component

Allows admin to:

- Add faculty
- Update faculty details
- Assign departments
- Manage faculty records

#### Course Allocation Component

Allows admin to assign courses to students and faculty.

#### Reports Component

Generates reports related to:

- Attendance
- Course registrations
- Faculty workload
- Student performance

#### System Notification Component

Sends important updates to students and faculty.

---

## 🔗 Which Components Communicate With Each Other?

### Student Dashboard Communication

The Student Profile Component communicates with the Attendance Summary Component and Course List Component because the attendance and course details are linked to the selected student.

The Registration Component communicates with the Notification Component because after successful registration, the student should receive a confirmation message.

The Course List Component communicates with the Assignment Status Component because assignments are based on the courses selected by the student.

Example:

When a student registers for a course, the Registration Component sends the selected course details to the parent dashboard. The parent dashboard updates the Course List Component and also sends a message to the Notification Component.

---

### Faculty Dashboard Communication

The Course Management Component communicates with the Student List Component because faculty need to see the students enrolled in each course.

The Student List Component communicates with the Attendance Update Component because attendance is updated for selected students.

The Assignment Review Component communicates with the Notification Component because students may receive feedback or reminders based on assignment status.

Example:

When faculty selects a course, the Student List Component displays all students in that course. Then faculty can update attendance using the Attendance Update Component.

---

### Admin Dashboard Communication

The Student Management Component communicates with the Course Allocation Component because students must be assigned to courses.

The Faculty Management Component communicates with the Course Allocation Component because faculty must be assigned to courses.

The Course Allocation Component communicates with the Reports Component because course allocation data is required for generating reports.

The System Notification Component communicates with all other components because students and faculty need updates about changes.

Example:

When admin assigns a course to a faculty member, the Course Allocation Component updates the database and the System Notification Component sends information to the faculty.

---

## 🔄 Data Flow Explanation

For the data flow task, I chose the process:

## Student Registration

Student registration is a common process in an academic application. It includes taking student details from the UI, validating the details, processing the data, storing it in the database, and sending a notification.

---

## Student Registration Data Flow

### Complete Flow

UI → Validation → Flow → Apex → Database → Notification

---

## 1. UI

The process starts from the user interface.

The student opens the registration form and enters details such as:

- Name
- Roll number
- Email
- Department
- Year
- Course selection
- Phone number

The UI is usually built using Lightning Web Components. It provides input fields, buttons, dropdowns, and messages to help the student complete registration.

Example:

A student fills the registration form and clicks the "Submit" button.

---

## 2. Validation

After the student submits the form, validation is performed.

Validation checks whether the entered data is correct or not.

Examples of validation:

- Name should not be empty.
- Email should be in correct format.
- Roll number should be unique.
- Phone number should contain valid digits.
- Required fields should be filled.
- Course selection should not be empty.

Validation is important because incorrect data should not be stored in the database.

Example:

If a student enters an invalid email, the system shows an error message and asks the student to correct it.

---

## 3. Flow

After successful validation, the data moves to the business process flow.

Salesforce Flow can be used to automate steps in the registration process.

Flow can perform actions such as:

- Checking whether the student already exists
- Assigning the student to a department
- Creating registration records
- Sending data to Apex if complex logic is required
- Triggering notifications

Example:

The flow checks whether the student roll number is already present. If not, it continues the registration process.

---

## 4. Apex

Apex is used when custom backend logic is required.

Apex can handle complex operations such as:

- Checking duplicate records
- Applying business rules
- Inserting records
- Updating related objects
- Handling errors
- Connecting with other systems

Example:

Apex checks whether the selected course has available seats. If seats are available, it allows the student to register.

---

## 5. Database

After processing, the data is stored in the Salesforce database.

The database may store records in objects such as:

- Student Object
- Course Object
- Registration Object
- Attendance Object
- Notification Object

Example:

The student's registration details are saved as a new record in the Registration object.

---

## 6. Notification

After successful registration, the system sends a notification.

The notification may be shown on the screen or sent through email.

Example messages:

- "Registration completed successfully."
- "You have successfully registered for the selected course."
- "Your registration is pending admin approval."

Notifications help the user know the result of their action.

---

## Complete Student Registration Flow in Simple Words

First, the student opens the registration form in the UI and enters all required details. After clicking submit, the system validates the information to make sure all fields are correct. Then the data goes through Salesforce Flow, where the registration process is automated. If any complex logic is needed, Apex handles it in the backend. After that, the registration details are saved in the Salesforce database. Finally, the student receives a notification confirming whether the registration was successful or not.

---

## ⚡ Modern vs Legacy Thinking

## Why Did Salesforce Move from Visualforce and Aura to LWC?

Salesforce moved from Visualforce and Aura Components to Lightning Web Components because LWC is faster, more modern, lightweight, and based on standard web technologies.

---

## Visualforce

Visualforce is an older Salesforce UI framework. It uses a page-based approach and is similar to traditional web development. Visualforce was useful earlier, but it is not the best choice for modern dynamic applications.

### Limitations of Visualforce

- Page reloads are common.
- Less dynamic compared to modern frameworks.
- Performance is slower for interactive UI.
- Not fully component-based like LWC.
- More difficult to build modern responsive applications.

---

## Aura Components

Aura Components were introduced after Visualforce to support component-based development. Aura allowed developers to build reusable components and dynamic pages.

### Limitations of Aura

- More complex syntax.
- Heavier framework.
- Performance is lower compared to LWC.
- Less aligned with modern JavaScript standards.
- More code is required for simple tasks.

---

## Lightning Web Components

Lightning Web Components is the modern Salesforce UI framework. It uses standard web technologies such as:

- HTML
- CSS
- JavaScript
- Web Components

LWC is faster because it uses browser-native features. It is also easier to learn for developers who already know modern web development.

### Advantages of LWC

- Faster performance
- Lightweight framework
- Uses standard JavaScript
- Better browser compatibility
- Easy to reuse components
- Better security
- Better maintainability
- Suitable for enterprise applications
- Works well with Salesforce data
- Supports modern UI architecture

---

## Aura vs LWC

| Feature | Aura Components | Lightning Web Components |
|---|---|---|
| Technology | Salesforce-specific framework | Based on standard web technologies |
| Performance | Slower compared to LWC | Faster and lightweight |
| Syntax | More complex | Cleaner and simpler |
| Browser Support | Uses framework layer | Uses browser-native features |
| Reusability | Supports reusable components | Better reusable component structure |
| Learning Curve | More difficult | Easier for web developers |
| Modern Development | Older approach | Modern approach |
| Best Use | Existing Aura applications | New Salesforce development |

---

## Why LWC is Better for Modern Salesforce Applications

LWC is better because it follows modern frontend development standards. It improves performance, reduces complexity, and makes applications easier to maintain. Since enterprise applications need speed, scalability, and reusability, LWC is the preferred framework for Salesforce development.

In simple words, Salesforce moved toward LWC because modern applications need fast loading, reusable components, clean code, and better user experience.

---

## 🧱 Modular Architecture

Modular architecture means dividing a large application into smaller independent modules or components.

Each module performs a specific task. These modules can communicate with each other to create a complete application.

Example:

Instead of building one large dashboard with all code inside one file, we divide it into separate components:

- Profile Component
- Attendance Component
- Course Component
- Notification Component
- Report Component

This makes the application easier to understand, develop, test, and maintain.

---

## Why Enterprise Applications Need Modular Architecture

Enterprise applications are usually large and complex. They may have many users, roles, features, and business processes. If the full application is built as one large system, it becomes difficult to manage.

Modular architecture is needed because:

- It improves code reusability.
- It makes the application easier to maintain.
- It allows teams to work on different modules separately.
- It reduces duplicate code.
- It improves testing.
- It makes debugging easier.
- It supports scalability.
- It reduces the risk of breaking the full application.
- It helps in adding new features easily.

Example:

In a college management system, student registration, attendance, course allocation, and reports can be separate modules. If we need to update the attendance module, we can do it without disturbing the complete system.

---

## 🔐 Why UI and Backend Should Remain Separate

UI and backend should remain separate because both have different responsibilities.

The UI is responsible for:

- Displaying data
- Taking user input
- Showing buttons and forms
- Giving a good user experience

The backend is responsible for:

- Processing business logic
- Validating important rules
- Saving data
- Updating records
- Handling security
- Communicating with the database

Keeping UI and backend separate makes the application cleaner, safer, and easier to maintain.

Example:

The UI collects student registration details, but the backend checks whether the roll number is unique and stores the record in the database.

---

## ⚠️ Problems in Tightly Coupled Systems

A tightly coupled system means components are highly dependent on each other. If one component changes, other components may also break.

Problems in tightly coupled systems:

- Difficult to update
- Difficult to test
- Difficult to reuse code
- One small change can affect many parts
- Debugging becomes hard
- Development becomes slower
- Not suitable for large applications
- Scaling becomes difficult

Example:

If attendance logic, student details, and notification code are all written inside one component, changing attendance logic may accidentally break notifications or student details.

This is why loosely coupled and modular design is better.

---

## 🌐 Why Frontend Architecture is Important

Frontend architecture is important because users directly interact with the frontend. A well-designed frontend improves user experience and makes the application easy to use.

Good frontend architecture helps in:

- Creating reusable components
- Improving performance
- Making UI responsive
- Handling user actions properly
- Managing data flow clearly
- Reducing code duplication
- Making the application easier to update

Example:

A student dashboard should clearly show attendance, courses, assignments, and notifications. If the frontend architecture is poor, users may get confused and the system becomes difficult to use.

---

## ♻️ Why Large Systems Need Reusable Modules

Large systems need reusable modules because the same functionality may be required in many places.

Example:

A Notification Component can be used in:

- Student Dashboard
- Faculty Dashboard
- Admin Dashboard

Instead of writing notification logic again and again, we can create one reusable component and use it in different dashboards.

Benefits of reusable modules:

- Saves development time
- Reduces duplicate code
- Improves consistency
- Easier to maintain
- Easier to test
- Supports faster development

---

## 💭 Reflection

Today I learned that enterprise applications are not built as one large block. They are divided into smaller components that communicate with each other. This makes applications more flexible, reusable, and scalable.

I understood that Lightning Web Components are important because they support modern UI development in Salesforce. LWC uses standard web technologies and provides better performance compared to Visualforce and Aura.

I also learned how data flows from the UI to validation, then to Flow, Apex, database, and finally notification. This helped me understand how real-world Salesforce applications process user actions.

Modular architecture is very important in enterprise applications because it makes large systems easier to manage. If every feature is separated into reusable components, developers can update, test, and improve the application without affecting the complete system.

Overall, Day 9 helped me understand component communication, application architecture, and why LWC is important for building modern Salesforce applications.

---

## ✍️ Revision Questions and Answers

### 1. Why do components communicate?

Components communicate because applications are divided into smaller reusable parts. One component may need to send data or messages to another component. Communication helps components work together and create a dynamic user experience.

Example:

A Student Dashboard component sends attendance data to the Attendance Summary component.

---

### 2. Difference between parent-child communication and events?

Parent-child communication means the parent component sends data to the child component using properties.

Events are mainly used when the child component needs to send information back to the parent component or notify that something has happened.

In simple words:

- Parent to child: Data is passed from parent to child.
- Child to parent: Events are used to send information from child to parent.

Example:

Parent sends student details to child component. Child sends an event when the student clicks submit.

---

### 3. Why is modular architecture useful?

Modular architecture is useful because it divides a large application into smaller parts. Each part has a specific responsibility. This makes the application easier to develop, test, update, and maintain.

It also improves reusability and scalability.

Example:

A dashboard can be divided into Profile, Attendance, Courses, and Notifications components.

---

### 4. Why did Salesforce move toward LWC?

Salesforce moved toward LWC because LWC is faster, lightweight, and based on modern web standards like HTML, CSS, JavaScript, and Web Components.

LWC gives better performance than Visualforce and Aura. It is easier to maintain and suitable for modern enterprise applications.

---

### 5. What problems happen in tightly coupled systems?

In tightly coupled systems, components depend too much on each other. If one component changes, other components may break.

Problems include:

- Difficult maintenance
- Hard debugging
- Low reusability
- More errors
- Slower development
- Difficult testing
- Poor scalability

---

### 6. Why is frontend architecture important?

Frontend architecture is important because it controls how users interact with the application. A good frontend architecture makes the application easy to use, responsive, reusable, and maintainable.

It also helps developers manage UI components and data flow clearly.

---

### 7. Why should UI and backend remain separate?

UI and backend should remain separate because they have different responsibilities.

The UI handles user interaction and display. The backend handles logic, validation, database operations, and security.

Keeping them separate makes the application clean, secure, and easier to maintain.

---

### 8. Why do large systems need reusable modules?

Large systems need reusable modules to avoid writing the same code again and again. Reusable modules save time, reduce errors, and make the system consistent.

Example:

A Notification Component can be reused in Student, Faculty, and Admin dashboards.

---

## ✅ End of Day Outcome

After completing Day 9, I understood:

- Component communication in Lightning Web Components
- Parent-child communication
- Event-driven UI behavior
- Data flow in Salesforce applications
- Dashboard architecture
- Difference between Visualforce, Aura, and LWC
- Importance of modular enterprise architecture
- Why LWC is important in Salesforce
- Why large applications need reusable components

---

## 📁 GitHub Folder Structure

The GitHub submission folder for Day 9 should be:

```text
salesforce-training/
└── week2/
    └── day9-lwc-communication/
        └── README.md
