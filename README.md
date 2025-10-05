# Assignment II: Database Creation, Deletion & OEM

**Student:** Fatime Dadi Wardougou  
**Student ID:** 25858  
**Course:** Database Development with PL/SQL (INSY 8311)  
**Date:** October 5, 2025  

---

## 📘 Overview of Tasks

This assignment demonstrates proficiency in **Oracle Database 21c** Container and Pluggable Database (CDB/PDB) management and **Oracle Enterprise Manager (OEM)** configuration.

---

## 🧩 Task 1: Create a New Pluggable Database (PDB) 

**PDB Name:** `fa_pdb_25858`  
**User:** `fatime_plsqlauca_25858`  
**Password:** `auca2020`  

### ✅ Commands Used
```sql
CREATE PLUGGABLE DATABASE fa_pdb_25858
ADMIN USER fatime_plsqlauca_25858 IDENTIFIED BY auca2020
CREATE_FILE_DEST = 'D:\\ORACLE21CHOME\\ORADATA\\ORCL\\';

📸 Screenshots
<img width="674" height="383" alt="Task1 (2)" src="https://github.com/user-attachments/assets/c587898a-6c9d-40be-98cc-7000830f32ed" />


📸 Screenshots
<img width="813" height="307" alt="Task1_aftercreation" src="https://github.com/user-attachments/assets/c6d56cf9-0fb8-4a61-8092-f793bc4d0031" />


🗑️ Task 2: Create and Delete a PDB 

PDB Name: fa_to_delete_pdb_25858
User: fatime_delete_25858

📸 Screenshots
<img width="443" height="113" alt="Task2_creation" src="https://github.com/user-attachments/assets/663a09c3-4435-46d9-bbd7-6eaae1317504" />

📸 Screenshots
<img width="543" height="121" alt="Task2_after_creation" src="https://github.com/user-attachments/assets/d61a4d0a-0aaf-45c3-b034-1ebf99bdc8f5" />

📸 Screenshots
<img width="553" height="126" alt="Task2_deletion" src="https://github.com/user-attachments/assets/37f25032-4dcd-4b3d-9bef-7048e9550406" />


🖥️ Task 3: Oracle Enterprise Manager (OEM) 
Configuration Steps
Always show details
EXEC DBMS_XDB_CONFIG.SETHTTPPORT(8080);
EXEC DBMS_XDB_CONFIG.SETHTTPSPORT(5500);

SELECT DBMS_XDB_CONFIG.GETHTTPPORT() AS HTTP_PORT, 
       DBMS_XDB_CONFIG.GETHTTPSPORT() AS HTTPS_PORT 
FROM DUAL;


Access Path: https://localhost:5500/em
Login Credentials: system / auca2020

📸 Screenshots

<img width="607" height="319" alt="task3_completed_task1,2" src="https://github.com/user-attachments/assets/d1c6ccf6-cb0b-41e7-a8ad-bdef017f9cc3" />

📸 Screenshots
<img width="925" height="418" alt="task3_2" src="https://github.com/user-attachments/assets/ccfaffe1-1ed8-4b62-8356-ae7d20ff146c" />

📸 Screenshots
<img width="941" height="402" alt="task3_2_1" src="https://github.com/user-attachments/assets/9dacc2c9-5ce5-486f-ac9c-a8164dd38a48" />


⚙️ Issues Encountered & Solutions
🧱 Issue 1: File Path Errors During PDB Creation

Problem: ORA-65005: missing or invalid file name pattern
Solution: Replaced FILE_NAME_CONVERT with CREATE_FILE_DEST, which worked successfully.

🔐 Issue 2: SQL*Plus Connection and SYSDBA Access

Problem: Unable to connect as SYSDBA from SQL*Plus login.
Solution: Used sqlplus sys/auca2020 AS SYSDBA directly from CMD.

🌐 Issue 3: OEM Configuration and Access

Problem: Bad Request errors and invalid credential access.
Solution: Used HTTPS port 5500 and system login credentials with empty container name.

🧾 Issue 4: PDB Deletion Verification

Solution: Verified deletion via:

SQL*Plus DROP PLUGGABLE DATABASE output

ORA-65011 confirmation message

OEM Performance → Containers showing only active PDBs

🧠 Technical Environment
Component	Details
Database Version	Oracle Database 21c Enterprise Edition
Container Database	ORCL
Pluggable Databases	ORCLPDB, FA_PDB_25858
OEM Ports	HTTP = 8080, HTTPS = 5500
Connection	Localhost
Directory	D:\ORACLE21CHOME\ORADATA\ORCL\
💡 Key Learnings

CREATE_FILE_DEST is more reliable than FILE_NAME_CONVERT for new PDB creation.

SYSDBA connections must start from CMD, not within SQL*Plus login prompt.

OEM’s Performance → Containers view provides strong verification of PDB status.

Systematic troubleshooting ensures reliable Oracle configuration management.

🏁 Conclusion

All assignment requirements were successfully completed:

✅ Task 1: Created PDB fa_pdb_25858 using correct conventions.
✅ Task 2: Created and deleted fa_to_delete_pdb_25858 with full verification.
✅ Task 3: Configured and verified OEM dashboard displaying accurate PDB data.

This work demonstrates solid understanding of Oracle Multitenant Architecture, PDB lifecycle management, and OEM configuration with strong problem-solving under real-world constraints.

Prepared by:
👩‍💻 Fatime Dadi Wardougou (ID: 25858)

