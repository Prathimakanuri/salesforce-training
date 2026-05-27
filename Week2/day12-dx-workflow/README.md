# Salesforce Summer Program – Day 12  
## Professional Salesforce Developer Workflow

## Goal of the Day

The goal of Day 12 is to understand the **professional Salesforce developer workflow** used in real companies. Until now, we learned about Salesforce applications, automation, UI, and backend logic. Today’s focus is on how real Salesforce teams develop collaboratively using Salesforce DX, CLI, GitHub, version control, deployment workflows, and enterprise engineering practices.

---

## What is Salesforce DX?

Salesforce DX stands for **Salesforce Developer Experience**. It is a modern development approach that helps Salesforce developers build, test, and deploy applications in a professional and organized way.

In traditional Salesforce development, many changes are done directly in the browser using Setup. This is useful for learning and small tasks, but in real companies, developers need a more structured workflow. Salesforce DX supports **source-driven development**, where the code and metadata are stored in files and managed using version control systems like GitHub.

Salesforce DX helps developers work with Salesforce projects using tools such as:

- Salesforce CLI
- VS Code
- GitHub
- Scratch orgs
- Source control
- Deployment commands
- Testing workflows

Salesforce DX makes Salesforce development more professional, repeatable, and team-friendly.

---

## Why CLI Matters

CLI means **Command Line Interface**. Salesforce CLI allows developers to interact with Salesforce using commands instead of only clicking inside the browser.

The CLI matters because it improves developer productivity. Instead of manually performing every task in Salesforce Setup, developers can use commands to create projects, authorize orgs, deploy code, retrieve metadata, run tests, create scratch orgs, and manage development environments.

For example, developers can use CLI commands to:

- Create a Salesforce DX project
- Connect VS Code with a Salesforce org
- Deploy metadata to an org
- Retrieve changes from an org
- Run Apex tests
- Create and delete scratch orgs
- Push and pull source code
- Automate repetitive tasks

Using CLI saves time and reduces manual mistakes. In professional development, CLI is very important because teams need speed, accuracy, and automation.

---

## Why GitHub Matters

GitHub is a platform used for **version control and collaboration**. It helps developers store code, track changes, and work together on the same project.

In Salesforce development, GitHub is important because many developers may work on the same Salesforce application. Without GitHub, it becomes difficult to know who changed what, when the change was made, and why it was made.

GitHub helps teams by providing:

- Version history
- Branches for separate development
- Pull requests for review
- Collaboration between developers
- Backup of project files
- Easy rollback to previous versions
- Tracking of bugs and changes

GitHub makes Salesforce development safer and more organized. If a mistake happens, the team can check the older version and restore the correct code.

---

## Why Professional Developers Use GitHub, CLI, and DX Instead of Only Browser Clicks

Professional developers use GitHub, CLI, and Salesforce DX because browser clicks alone are not enough for large real-world projects.

Browser-based development is useful for beginners and simple configuration tasks. But in professional companies, Salesforce projects are usually large, team-based, and business-critical. Developers need proper control over code, testing, deployment, and rollback.

### GitHub helps with:
- Tracking every change
- Working in teams
- Reviewing code before deployment
- Maintaining different versions of the project
- Recovering previous working versions

### CLI helps with:
- Faster development
- Running commands quickly
- Deploying and retrieving metadata
- Automating repeated tasks
- Managing Salesforce orgs efficiently

### Salesforce DX helps with:
- Source-driven development
- Modern project structure
- Better collaboration
- Development in scratch orgs and sandboxes
- Professional deployment workflow

Therefore, professional developers prefer GitHub, CLI, and DX because they make Salesforce development more reliable, scalable, and suitable for enterprise projects.

---

## Team Collaboration Thinking

Suppose 10 developers are working on the same Salesforce project. Without version control, branches, and deployment workflow, many problems can happen.

### Problems Without Version Control

If there is no version control, developers cannot track changes properly. One developer may change a file, and another developer may overwrite it accidentally. The team will not know who made a mistake or when the mistake happened.

Without version control:

- Code changes can be lost
- Mistakes are difficult to find
- Developers may overwrite each other’s work
- There is no proper history of changes
- Rollback becomes difficult
- Team coordination becomes weak

### Problems Without Branches

Branches allow developers to work separately without disturbing the main project. If there are no branches, all developers may directly change the same project files.

Without branches:

- Incomplete features may affect the main project
- Bugs can enter the working code
- Testing becomes difficult
- Developers cannot safely experiment
- The main project may become unstable

### Problems Without Deployment Workflow

Deployment workflow is the process of moving changes from development to testing and then to production in a controlled way.

Without deployment workflow:

- Wrong code may go to production
- Untested features may affect users
- Business operations may fail
- There may be no approval process before release
- Rollback becomes difficult
- System reliability decreases

In enterprise projects, collaboration tools and deployment workflows are necessary because many developers work together and the system must remain stable.

---

## Enterprise Workflow Discussion

Enterprise software development is very different from college coding assignments.

### College Coding Assignments

In college coding assignments, usually one student works on a small program. The main goal is to complete the task and get the output. The project is usually short and simple.

College assignments usually focus on:

- Writing correct code
- Getting expected output
- Submitting before deadline
- Learning concepts
- Working individually
- Small-scale testing

If a mistake happens in a college assignment, the impact is small. It may affect only marks or submission.

### Enterprise Software Development

Enterprise software development is used in real companies where applications are used by many users and customers. The software must be reliable, secure, tested, and easy to maintain.

Enterprise development focuses on:

- Team collaboration
- Version control
- Testing
- Deployment
- Rollback
- Reliability
- Security
- User impact
- Business continuity
- Long-term maintenance

In enterprise software, even a small mistake can affect customers, employees, sales, data, or business operations. That is why companies follow a proper engineering workflow.

---

## Comparison: College Coding Assignments vs Enterprise Software Development

| Point | College Coding Assignments | Enterprise Software Development |
|------|-----------------------------|--------------------------------|
| Team Size | Mostly individual | Many developers work together |
| Code Size | Small programs | Large applications |
| Testing | Basic output checking | Unit testing, integration testing, regression testing |
| Collaboration | Limited | Strong collaboration required |
| Version Control | Sometimes not used | Mandatory |
| Deployment | Simple submission | Controlled deployment process |
| Rollback | Usually not needed | Very important |
| Reliability | Less critical | Highly critical |
| Impact | Affects marks | Affects real users and business |
| Tools Used | IDE/compiler | GitHub, CLI, CI/CD, Salesforce DX, sandboxes |

---

## Testing in Enterprise Workflow

Testing is very important in enterprise software development. Before deploying any change to production, developers must test the code properly.

Testing helps to:

- Find bugs early
- Ensure features work correctly
- Prevent production failures
- Maintain system quality
- Increase user trust

In Salesforce, Apex tests and validation are important before deployment. Testing ensures that new changes do not break existing features.

---

## Collaboration in Enterprise Workflow

Collaboration means multiple developers working together in an organized way. In large Salesforce projects, admins, developers, testers, and managers may all work on the same system.

Good collaboration requires:

- Clear communication
- GitHub repositories
- Branching strategy
- Code reviews
- Pull requests
- Task tracking
- Deployment planning

Without collaboration, the project becomes confusing and risky.

---

## Deployment in Enterprise Workflow

Deployment means moving changes from one environment to another, such as from development to testing or production.

In professional Salesforce development, changes should not be directly made in production. Developers usually work in development orgs or sandboxes first. After testing, the changes are deployed to production.

A good deployment workflow helps to:

- Avoid production errors
- Test changes before release
- Maintain quality
- Follow approval processes
- Reduce business risk

---

## Rollback in Enterprise Workflow

Rollback means returning the system to a previous stable version when something goes wrong.

Rollback is important because even after testing, sometimes bugs may appear in production. If there is no rollback capability, the team may struggle to fix the issue quickly.

Rollback helps teams to:

- Recover from mistakes
- Restore stable code
- Reduce downtime
- Protect business operations
- Maintain customer trust

GitHub is very useful for rollback because it stores previous versions of project files.

---

## Reliability in Enterprise Workflow

Reliability means the system should work correctly and consistently for users. Enterprise systems must be reliable because many people depend on them for daily work.

Salesforce applications may handle customer data, sales processes, service requests, automation, and reports. If the system fails, it can affect the company’s operations.

A professional workflow improves reliability through:

- Testing
- Version control
- Code reviews
- Deployment planning
- Rollback support
- Separate development and production environments

---

## Why Teams Separate Development and Production

Teams separate development and production because production is used by real users. If developers directly change production, mistakes can affect customers and employees.

Development environments are used for building and testing. Production is used for live business operations.

Separating development and production helps to:

- Test safely
- Avoid live system errors
- Protect business data
- Reduce risk
- Allow experimentation
- Maintain system stability

Salesforce sandboxes and scratch orgs are useful for this purpose.

---

## Why Source-Driven Development is Useful

Source-driven development means the source code and metadata are stored and managed as files. These files are usually tracked using GitHub.

Source-driven development is useful because it gives teams better control over the project.

Benefits of source-driven development:

- Easy tracking of changes
- Better team collaboration
- Code review before deployment
- Simple rollback
- Clear project structure
- Automation support
- Better release management

Salesforce DX supports source-driven development and makes Salesforce projects easier to manage professionally.

---

## Reflection

After learning about Salesforce DX, CLI, GitHub, and professional Salesforce workflow, I realized that software engineering is not only about writing code or completing tasks. Real professional development requires planning, teamwork, testing, version control, deployment, rollback, and reliability.

In college assignments, we usually focus on completing the program and getting the correct output. But in enterprise software development, the application is used by real users and businesses. So every change must be handled carefully.

I understood that GitHub is important for tracking changes and collaboration. CLI is important for productivity and automation. Salesforce DX is important because it supports modern source-driven development and helps teams work in a professional way.

I also realized that large projects cannot be managed only with browser clicks. Professional teams need proper tools and workflows to avoid mistakes, protect production systems, and deliver reliable software.

This day helped me understand how real Salesforce developers work in companies and why engineering workflow is important for successful software development.

---

# Revision Questions and Answers

## 1. Why do enterprise teams use version control?

Enterprise teams use version control to track changes, collaborate safely, maintain history, and recover previous versions when needed. It helps developers know who changed what and when. Version control also prevents loss of code and supports teamwork through branches and pull requests.

---

## 2. Why is deployment workflow important?

Deployment workflow is important because it controls how changes move from development to testing and production. It ensures that only tested and approved changes are released. This reduces the risk of errors in production and protects real users from unstable features.

---

## 3. What problems happen without collaboration tools?

Without collaboration tools, developers may overwrite each other’s work, lose changes, create duplicate work, and face confusion about project updates. It becomes difficult to track tasks, review code, and manage team communication. This can lead to bugs and project delays.

---

## 4. Why is Salesforce DX important?

Salesforce DX is important because it provides a modern developer workflow for Salesforce projects. It supports source-driven development, CLI usage, scratch orgs, GitHub integration, and better deployment practices. It helps teams build Salesforce applications in a more professional and organized way.

---

## 5. Why do developers prefer CLI tools?

Developers prefer CLI tools because they are faster, more powerful, and useful for automation. CLI allows developers to create projects, deploy code, retrieve metadata, run tests, and manage orgs using commands. This saves time and reduces manual work.

---

## 6. Why do enterprise systems require rollback capability?

Enterprise systems require rollback capability because mistakes can happen during deployment. If a new change causes an issue, rollback allows the team to return to a previous stable version. This reduces downtime, protects users, and keeps the business running smoothly.

---

## 7. Why should teams separate development and production?

Teams should separate development and production because production is used by real users. Developers need a safe place to build and test changes without affecting live business operations. Separate environments reduce risk and improve system stability.

---

## 8. Why is source-driven development useful?

Source-driven development is useful because it stores project code and metadata as files that can be tracked in version control. It improves collaboration, testing, deployment, rollback, and project organization. It also helps teams understand the complete history of the project.

---

## 9. Why is collaboration difficult in large projects?

Collaboration is difficult in large projects because many developers may work on the same files, features, and environments. Without proper tools, communication gaps, code conflicts, duplicate work, and deployment errors can happen. Large projects need GitHub, branches, reviews, and clear workflows to manage collaboration.

---

## 10. Why is engineering workflow important?

Engineering workflow is important because it provides a structured process for building, testing, deploying, and maintaining software. It helps teams work efficiently, avoid mistakes, improve quality, and deliver reliable applications. In enterprise systems, a good workflow protects both the business and the users.

---

## End of Day Outcome

By completing Day 12, I understood the importance of professional Salesforce development workflow. I learned why Salesforce DX, CLI, and GitHub are important in real-world development. I also understood the challenges of team collaboration and why enterprise software development requires testing, deployment planning, rollback, and reliability.

Day 12 helped me understand how Salesforce development happens in professional teams and how modern tools support better software engineering practices.
