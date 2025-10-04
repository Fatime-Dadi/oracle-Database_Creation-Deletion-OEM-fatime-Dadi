# Assignment II: Database Creation, Deletion & OEM

**Student:** Fatime Dadi Wardougou  
**Student ID:** 25858  
**Course:** Database Development with PL/SQL (INSY 8311)  
**Date:** October 4, 2025  

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

task1_pdb_creation.png – Successful creation of fa_pdb_25858

task1_pdb_verification.png – Verification of PDB in READ WRITE mode

🗑️ Task 2: Create and Delete a PDB 

PDB Name: fa_to_delete_pdb_25858
User: fatime_delete_25858

📸 Screenshots

task2_pdb_creation.png – Creation of fa_to_delete_pdb_25858

task2_both_pdbs_exist.png – Both FA_PDB_25858 and FA_TO_DELETE_PDB_25858 visible

task2_deletion_commands.png – Deletion commands executed successfully

task2_final_verification.png – Final verification showing deletion complete

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

task3_oem_dashboard.png – OEM Dashboard showing CDB with 2 active PDBs

task3_oem_containers.png – OEM “Containers” view confirming only active PDBs

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

