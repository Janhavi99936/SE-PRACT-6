A UML Package Diagram is a structural diagram that groups related elements (classes, interfaces, or other packages) of a system into packages. It shows the organization of a system at a high level and the dependencies between different packages. Package diagrams are especially useful for large systems, where they help visualize how the system is modularized and how different modules interact with one another.

Notation Used
Package – represented as a folder-shaped rectangle (a tab on top and a larger rectangle below), labeled with the package name.
Class inside a package – shown as a smaller rectangle nested within the package, sometimes annotated with (from PackageName) to indicate its origin.
Dependency relationship – represented by a dashed arrow pointing from the package that depends on another package, optionally labeled with a stereotype such as use, import, or a custom role name (e.g. attempts, evaluates).
Case Study: Online Examination System

The Online Examination System allows students to register, log in, attempt exams created by administrators/examiners, and view their evaluated results. The system was decomposed into the following packages:

Package	Description
User Management	Manages user accounts — contains Student and Admin classes.
Authentication	Handles login, session management, and access control — contains the Login class.
Exam Management	Handles creation and scheduling of exams — contains the Exam class.
Question Bank	Stores and manages exam questions — contains the Question class.
Exam Attempt Management	Manages a student's attempt at an exam — contains the ExamAttempt class.
Evaluation Management	Evaluates submitted answers and generates results — contains the Result class.
Reporting and System Service	Generates reports and sends notifications — contains ReportService and NotifyService classes.
Dependencies Between Packages
User Management → Exam Management : use
Exam Management → Question Bank : contains
User Management → Authentication : use
Exam Management → Exam Attempt Management : attempts
Exam Attempt Management → Evaluation Management : evaluates
Exam Attempt Management → Question Bank : answers
Authentication → Reporting and System Service : use
Evaluation Management → Reporting and System Service : generates

Steps to Create the Diagram in StarUML
Open StarUML and create a new project.
Right-click on the model in the Model Explorer → Add Diagram → Package Diagram.
From the Toolbox, drag and drop the Package element onto the canvas for each package (User Management, Authentication, Exam Management, Question Bank, Exam Attempt Management, Evaluation Management, Reporting and System Service).
Inside each package, add the relevant Class element(s) (e.g. Student, Admin inside User Management).
Use the Dependency tool from the Toolbox to draw dashed arrows between packages, and set the name property of each dependency (e.g. use, contains, attempts) in the Properties panel.
Arrange the packages for clarity and export the diagram as an image (File → Export Diagram → PNG/SVG).
