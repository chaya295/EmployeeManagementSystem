# Employee Management System

A clean, fast, and practical Employee Management System built to help teams manage people — not paperwork. Designed for HR teams, managers, and small-to-medium businesses that want a simple, reliable way to store employee records, manage departments and roles, and export actionable reports.

Why this project?
-----------------
- Save time: Replace scattered spreadsheets with a single source of truth.
- Stay organized: Centralize employee data, roles, and department structure.
- Actionable insights: Exportable reports make payroll, headcount, and audits easier.
- Ready to integrate: Lightweight API-first design makes it easy to connect to existing tools.

Core features
-------------
- Full CRUD for employees (profile, contact, employment details)
- Department & role management
- Search, filtering and pagination
- CSV/Excel export for reports & payroll
- Basic role-based access (Admin / HR / Employee)
- Profile picture upload (optional)
- Audit-ready: history-friendly structure for tracking changes

Try it in 60 seconds
--------------------
1. Clone the repo:
```bash
git clone https://github.com/chaya295/EmployeeManagementSystem.git
cd EmployeeManagementSystem
```

2. Copy and configure environment:
```bash
cp .env.example .env
# Edit .env: DB_* and JWT_SECRET at minimum
```

3. Start the backend (example Node.js):
```bash
cd backend
npm install
npm run dev
```

Or using Docker:
```bash
docker-compose up --build
```

Minimal .env example
--------------------
```env
PORT=3000
NODE_ENV=development
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASS=yourpassword
DB_NAME=employee_db
JWT_SECRET=replace_with_a_strong_secret
```

API Highlights (examples)
-------------------------
- POST /api/auth/login — Sign in and receive JWT
- GET /api/employees — List employees (supports ?page=&limit=&search=)
- POST /api/employees — Create employee
- GET /api/employees/:id — Employee details
- PUT /api/employees/:id — Update employee
- DELETE /api/employees/:id — Remove employee
- GET /api/reports/employees?format=csv — Export employees as CSV

Why teams love it
-----------------
- Lightweight: Minimal setup; useful from day one.
- Extensible: Clear folder structure and API make adding features straightforward.
- Practical: Focus on the everyday HR needs — search, edit, export.
- Production-ready patterns: Environment-based config, recommended Docker setup, and CI-friendly workflows.

Testing & Quality
-----------------
- Run the test suite:
```bash
npm test
```
- Recommended: enable CI (GitHub Actions) to run tests and linting on every PR.

Deployment & Security
---------------------
- Use Docker for consistent deployments; use your cloud provider’s secrets manager for credentials.
- Never commit secrets to the repository.
- Use HTTPS in production and enforce reasonable JWT expiry and password hashing (bcrypt).

