# 🏥 Hospital Database Management System (SQL Project)

## 📌 Project Overview

This is a comprehensive **Hospital Management System** developed in **SQL** as part of a database course project. It is designed to handle hospital operations such as:

- Managing patient and employee data
- Scheduling appointments and operations
- Processing prescriptions and billing
- Tracking room assignments and insurance coverage

The system uses a normalized relational database schema and includes stored procedures, views, triggers, and queries to simulate real-world hospital operations.

---

## 🎯 Objectives

- Build a fully functional relational database system.
- Apply **Normalization (up to 3NF)** to avoid redundancy.
- Write SQL queries for CRUD operations, reporting, and analysis.
- Implement **stored procedures**, **views**, and **triggers**.
- Simulate real-world hospital workflows and data integrity constraints.

---

## 🗃️ Database Schema Overview

The hospital database contains the following tables and components:

### 🧾 Main Tables

| Table Name       | Description |
|------------------|-------------|
| `patient`        | Stores patient details |
| `employee`       | Stores hospital staff details |
| `department`     | Contains hospital departments |
| `position`       | Lists job titles (e.g., Doctor, Nurse) |
| `appointment`    | Patient appointments with doctors |
| `operation`      | Details of surgical operations |
| `prescription`   | Medicines prescribed to patients |
| `invoice`        | Billing details and totals |
| `room`           | Room availability and patient assignments |
| `insuragency`    | Insurance company information |

### ⚙️ Supporting Functions / Views / Triggers

| Object Name           | Type           | Purpose |
|------------------------|----------------|---------|
| `check_funds`         | Procedure      | Checks insurance coverage |
| `count_patients`      | Function       | Returns total number of patients |
| `getempfullname`      | View           | Displays full name of employees |
| `updateroomstatus`    | Trigger        | Updates room status on patient check-in/out |
| `trg_employee_update` | Trigger        | Logs when employee last name is updated |

---

## 🧱 Entity Relationship Diagram (ERD)

*(Attach or link to `ERD_diagram.png` if available)*

Entities are linked using **primary and foreign key constraints**. The schema ensures **referential integrity** between tables such as:
- `PATIENT.EMP_ID` → `EMPLOYEE.EMP_ID`
- `EMPLOYEE.DEP_ID` → `DEPARTMENT.DEP_ID`
- `EMPLOYEE.POS_ID` → `POSITION.POS_ID`
- `APPOINTMENT.PAT_ID` → `PATIENT.PAT_ID`
- `INVOICE.PAT_ID` → `PATIENT.PAT_ID`

---

## ⚙️ Features Implemented

- ✅ Table creation with constraints (PK, FK, NOT NULL, etc.)
- ✅ Views for simplified reporting
- ✅ Stored procedures for automation
- ✅ Triggers to handle system updates
- ✅ Sample queries using joins, subqueries, aggregations

---

## 💻 Sample SQL Snippets

### 🔍 View: Patients Assigned to Doctors
<code>
SELECT PATIENT.PAT_FNAME, PATIENT.PAT_LNAME, EMPLOYEE.EMP_FNAME
FROM PATIENT
JOIN EMPLOYEE ON PATIENT.EMP_ID = EMPLOYEE.EMP_ID
WHERE EMPLOYEE.POS_ID IN (SELECT POS_ID FROM POSITION WHERE POS_NAME = 'Doctor'
);
</code>

## 🧪 Tools Used

- 💽 **Oracle SQL / SQL Developer** – for creating and testing the database  
- 🛠️ **ERD Tool** – lucidchart.com for designing the entity relationship diagram  
- 📝 **SQL Languages** – DDL, DML, DCL, TCL commands used for data creation and manipulation  
- 📄 **Microsoft Word** – for writing the final project report and documentation  

---

## 🚀 How to Run This Project

1. Open **Oracle SQL Developer** or any compatible SQL environment.
2. Run `create_tables.sql` to create all the database tables.
3. Run `insert_data.sql` to insert sample data into the tables.
4. Execute `views.sql`, `triggers.sql`, and `stored_procedures.sql` to set up logic components.
5. Run and experiment with `sample_queries.sql` to test and explore the system.

---

## 👥 Contributors

- **Natasha Linares**  
- **Jacob Kitchens**

---

## 📝 Notes

- This project was developed for **educational purposes** as part of a database course.
- All data used is **fictional** and intended only to demonstrate SQL capabilities.
- Final submission includes a **live SQL demo**, **project documentation**, and a **presentation** to the instructor.

