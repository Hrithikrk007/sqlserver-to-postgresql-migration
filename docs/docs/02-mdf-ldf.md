MDF and LDF Files — What They Are 
When SQL Server stores a database on disk, it uses two physical files: 
1.MDF — Primary Data File 
The MDF file is the main database file. It contains the entire database structure and all data 
— every table, index, view, stored procedure, constraint, and the actual row data. Every SQL 
Server database has exactly one primary MDF file. Think of it as the database itself in 
physical file form. 
2.LDF — Log Data File 
The LDF file is the transaction log. It records every single change made to the database — 
every INSERT, UPDATE, DELETE, and DDL statement — before those changes are written 
permanently to the MDF. It serves two critical purposes: 
• Crash recovery: if SQL Server crashes mid-transaction, the LDF is used to roll back 
incomplete transactions and restore the database to a consistent state 
• Point-in-time restore: using the LDF, a database can be restored to any specific 
moment in time, not just the last full backup. 
