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

![BPMN Diagram](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/patient.png)
Stores patient information:
- `patient_id` (Primary Key, Identity)
- `name`
- `age`
- `gender`
- `admitted_status` (`YES`/`NO`)
  ### Doctors Table

![BPMN Diagram](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/doctor.png)

Stores doctor information:
- `doctor_id` (Primary Key, Identity)
- `name`
- `specialty`
---
### inserting sample data in our table
