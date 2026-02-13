# oracle_pdb_ass_II_28840_benjamin

## 
Student ID: 28840
Name:Byiringiro Benjamin
--

## Overview

This assignment involved working with Oracle Database 19c using the multitenant architecture. The tasks included creating and managing Pluggable Databases (PDBs), creating users inside the PDB, deleting a temporary PDB, and accessing Oracle Enterprise Manager (OEM) to monitor the database environment. The assignment demonstrates practical skills in database administration and PDB management.


## Oracle Environment Used

- Oracle Database Version: 19c
- Tool Used: SQL Developer
- OEM: Oracle Enterprise Manager Express

                               Task1
  Create a New Pluggable Database

A new Pluggable Database (PDB) was created following the required naming convention. The PDB was opened in READ WRITE mode, and a local user was created inside it with the necessary privileges for future coursework.
reating a pluggable database here:

this is for creating PDB:
create PLUGGABLE DATABASE be_pdb_28840
ADMIN USER pdbadmin IDENTIFIED BY admin123
FILE_NAME_CONVERT = ('pdbseed','be_pdb_28840');
                         
                         creating the user in our PDB

CREATE USER benjamin_plsqlauca_28840 IDENTIFIED BY ben123;

-- so to be sure about your user you created just we find it using:
SELECT username FROM dba_users WHERE username = 'BENJAMIN_PLSQLAUCA_28840';

                          task 2
                          
## overview

A temporary PDB was created using the specified naming format. Its existence was verified, then it was properly closed and deleted completely, including its data files. Final verification confirmed that the PDB no longer existed. 

firstly we created a temporary PDB as, 

CREATE PLUGGABLE DATABASE be_to_delete_pdb_28840
ADMIN USER pdbadmin IDENTIFIED BY admin123
FILE_NAME_CONVERT = ('pdbseed','be_to_delete_pdb_28840');
 
 After we have to make our PDB open by
 ALTER PLUGGABLE DATABASE be_to_delete_pdb_28840 OPEN;
 
Dropping an existing PDB we do:

DROP PLUGGABLE DATABASE be_to_delete_pdb_28840 INCLUDING DATAFILES;

but before dropping it completely we have to close first our PDB we open before:
ALTER PLUGGABLE DATABASE be_to_delete_pdb_28840 CLOSE IMMEDIATE;




                         task 3
Oracle Enterprise Manager Express was configured and accessed through the browser. The dashboard was used to verify the Oracle environment, confirm the created PDB, and display the user account created inside the PDB.
as show below in the image

![task 3 3](https://github.com/user-attachments/assets/2005748b-8a39-471a-84fc-0818e0911c3e)




                         Conclusion

This tasks improve understanding of Oracle Multitenant Architecture, PDB lifecycle management, user administration, and Oracle Enterprise Manager monitoring.
