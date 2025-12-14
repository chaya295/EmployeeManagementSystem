
# Employee Management System

A clean, practical C# application for managing employee records — built for teams who want a lightweight, local solution that uses XML files for storage. Focused on clarity, reliability, and easy extensibility.

Highlights
- Simple CRUD for employee profiles
- Departments, roles and role-based access patterns (RBAC)
- XML-based storage (no external DB required)
- Export/import and report-ready data
- Clear separation: Presentation (PL) / Business Logic (BL) / Data Access (DAL)

Why use this project?
- Minimal setup — runs with dotnet and stores data in plain XML files you can inspect and version.
- Good for learning and small organizations that prefer file-based persistence.
- Modular architecture makes adding new UI layers or swapping storage straightforward.

What’s in this repo
- dotNet5785_6550_4998.sln — Visual Studio / .NET solution file
- PL/ — Presentation Layer (startup project; UI/console)
- BL/ — Business Logic layer
- DalList/ DalFacade/ DalXml/ — Data access implementations (XML-based)
- xml/ — sample XML data files used by the app
- BlTest/ DalTest/ — unit test projects

Quick start (build & run)
1. Clone the repo
   git clone https://github.com/chaya295/EmployeeManagementSystem.git
   cd EmployeeManagementSystem

2. Build the solution
   dotnet build

3. Run the application (example — replace `<project-path>` with actual startup project if different)
   dotnet run --project PL

Notes:
- If PL is a UI project that requires Visual Studio on Windows (WinForms/WPF), open the .sln in Visual Studio and run from there.
- If PL is a console app, the dotnet run command above will start it from the CLI.

Running tests
- Run all tests:
  dotnet test

XML storage & configuration
- The project uses XML files for persistence (see the xml/ directory).
- Look for a configuration value (e.g., in appsettings.json or a config class) that points to the XML file path. You can:
  - Edit the path to a writable folder
  - Inspect the XML files directly to verify stored data
- Back up XML files before running migration/transform operations.

Common tasks
- Add new employee: use the app’s UI or command flow; the DAL Xml implementation will update the XML file.
- Export data: there are export utilities (CSV/Excel) — check PL/ or BL/ for export commands or menus.

Architecture overview
- PL (Presentation Layer): UI and user interactions
- BL (Business Logic): validation, rules, and use-cases
- DAL (Data Access Layer): DAL Xml is the active persistence layer; DalList/DalFacade provide alternate implementations or patterns

