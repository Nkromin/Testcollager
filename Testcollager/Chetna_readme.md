Department & Employee API
🎯 What This Tests

FastAPI basics

Clean folder structure

Simple FK relationship

Basic service → CRUD separation

Confidence with ORM

📌 Problem Statement

Build a FastAPI REST API to manage Departments and Employees using PostgreSQL + SQLAlchemy.

📂 Required Folder Structure (Mandatory)
project/
│── main.py
│── routes/
│   ├── department_route.py
│   └── employee_route.py
│── services/
│   ├── department_service.py
│   └── employee_service.py
│── sql/
│   ├── database.py
│   ├── models.py
│   └── crud.py

🧱 Data Models
Department
Field	Type
id	int (PK)
name	string
Employee
Field	Type
id	int (PK)
name	string
role	string
department_id	FK → departments.id
🔁 Relationship Rules

One Department → Many Employees

Use:

relationship("Employee", back_populates="department")


No cascade required (keep it simple)

🛠️ Required APIs
Department APIs
POST /departments
GET  /departments

Employee APIs
POST /employees
GET  /employees

🧠 Business Rules (Very Simple)

1️⃣ An employee must belong to a department
2️⃣ Department must exist before adding employee
3️⃣ Validation should be in service layer

❌ Disallowed

No raw SQL

No global DB session

No business logic in crud.py