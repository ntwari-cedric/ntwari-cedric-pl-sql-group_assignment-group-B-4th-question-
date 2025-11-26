# ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-
# Hospital Management Package (Oracle PL/SQL)
---

## 👥 Group Members

1. **Ntambara Shema Chrispin** – 28280  
2. **Munyanturire Kaliza Liesse** – 28410  
3. **Himba Aimee Mireille** – 28220  
4. **Ntwari Cedric** – 28228  
5. **Singizwa Boncoeur** – 28308 
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
![cody](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/procedure%20og.png?raw=true)

![BPMN Diagram](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/procedure%20og2.png?raw=true)

## 🧪 Testing
Example test scripts are provided to validate functionality:

1. **Bulk Load Patients**
   ```sql
   DECLARE
       l_patients hospital_pkg.patient_tab := hospital_pkg.patient_tab();
   BEGIN
       l_patients.EXTEND(2);
       l_patients(1).name := 'Alice'; l_patients(1).age := 30; l_patients(1).gender := 'F'; l_patients(1).admitted_status := 'NO';
       l_patients(2).name := 'Bob';   l_patients(2).age := 45; l_patients(2).gender := 'M'; l_patients(2).admitted_status := 'NO';

       hospital_pkg.bulk_load_patients(l_patients);
   END;
   /
   
2.Show All Patients

sql
VARIABLE rc REFCURSOR;
EXEC :rc := hospital_pkg.show_all_patients;
PRINT rc;
3.Admit a Patient

sql
EXEC hospital_pkg.admit_patient(1);
/
4.Count Admitted Patients
sql
SELECT hospital_pkg.count_admitted FROM dual;
/
![exec](https://github.com/ntwari-cedric/ntwari-cedric-pl-sql-group_assignment-group-B-4th-question-/blob/main/ex.png?raw=true)

## Conclusion

In conclusion, all requirements were fully implemented, tested, and verified. The package provides efficient bulk data handling, clear information retrieval, and reliable patient admission management, proving the effectiveness of PL/SQL for real-world systems.
