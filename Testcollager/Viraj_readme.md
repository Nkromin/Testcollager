🧪 Coding Requirement 1
Course & Assignment Management API
⏱️ Time: 45 minutes
🎯 Tests: FastAPI, FK, service logic, cascade, clean layers
📌 Problem Statement

Build a FastAPI REST API to manage Courses and Assignments using PostgreSQL + SQLAlchemy.

📂 Mandatory Project Structure
project/
│── main.py
│── routes/
│   ├── course_route.py
│   └── assignment_route.py
│── services/
│   ├── course_service.py
│   └── assignment_service.py
│── sql/
│   ├── database.py
│   ├── models.py
│   └── crud.py

🧱 Data Models
Course
Field	Type
id	int (PK)
name	string
level	string ("beginner", "advanced")
Assignment
Field	Type
id	int (PK)
title	string
difficulty	string
course_id	FK → courses.id
🔁 Relationships

One Course → Many Assignments

Use relationship() and back_populates

Enable ORM cascade (all, delete)

🧠 Business Rules (Important)

1️⃣ Assignments are created automatically only when

course.level == "advanced"


2️⃣ Business logic must be in service layer

3️⃣ crud.py must only contain DB operations

🛠️ Required APIs
Course APIs
POST /courses
GET  /courses
DELETE /courses/{id}

Assignment APIs
GET /assignments
DELETE /assignments/{id}

🚨 Delete Behavior

Deleting an Assignment should:

Check its parent Course

If Course is "advanced", delete the Course as well

ORM cascade handles child cleanup

❌ Disallowed

Business logic in CRUD

Raw SQL

Hard-coded IDs

Global DB sessions