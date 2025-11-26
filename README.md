# ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-
# Hospital Management Package (Oracle PL/SQL)
---

## 👥 Group Members

1. **Ntambara Shema Chrispin** – 28280  
2. **Munyanturire Kaliza Liesse** – 28410  
3. **Himba Aimee Mireille** – 28220  
4. **Ntwari Cedric** – 28228  
5. **Singizwa Boncoeur** – 28228  
6. **Irembere Olivier** – 28392  
7. **Uwase Sonia Umutoni** – 28352

   ## 📖 Overview
This project implements a **Hospital Management Package** in Oracle PL/SQL to streamline patient and doctor management.  
It demonstrates the use of **bulk processing techniques (FORALL)**, modular design, and package-based development for efficient database operations.

The package provides functionalities to:
- Bulk insert patient records
- Display patient information
- Track admitted patients
- Update admission status

---

## Patients Table

![patients](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/patient.png)
Stores patient information:
- `patient_id` (Primary Key, Identity)
- `name`
- `age`
- `gender`
- `admitted_status` (`YES`/`NO`)
  ### Doctors Table

![doctors](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/doctor.png)

Stores doctor information:
- `doctor_id` (Primary Key, Identity)
- `name`
- `specialty`
---
### inserting sample data in our table
![inserting](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/insert%20pactient.png?raw=true)

## 📦 Package Specification
The package `hospital_pkg` defines:
- **Collection Type**: `patient_tab` for bulk patient processing
- **Procedures & Functions**:
  - `bulk_load_patients` – Insert multiple patients at once
  - `show_all_patients` – Return all patients via a cursor
  - `count_admitted` – Return number of admitted patients
  - `admit_patient` – Update a patient’s admission status

---
![BPMN Diagram](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/package%201.png?raw=true)
![BPMN Diagram](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/package%202.png?raw=true)
![BPMN Diagram](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/package%203.png?raw=true)
## ⚙️ Package Body
Implements the above specification using:
- **FORALL** for efficient bulk inserts
- **SYS_REFCURSOR** for flexible querying
- **COMMIT** statements for data consistency

---
