# MDF and LDF Files

## What are MDF and LDF?

SQL Server stores databases using two main files:

### MDF (Primary Data File)
- Contains actual data and schema
- Includes tables, indexes, views, procedures
- Every database has one MDF file

### LDF (Log Data File)
- Stores transaction logs
- Tracks every INSERT, UPDATE, DELETE
- Used for crash recovery and point-in-time restore

---

## How they are used in this project

- The database was already attached in SQL Server
- SQL Server reads MDF and LDF internally
- Data is exposed over TCP (port 1433)

---

## Key Insight

WSL does NOT directly access MDF/LDF files

Instead:

SQL Server → exposes data via TCP  
WSL → connects over network  
pgloader → reads data and migrates it  

---

## Flow

MDF/LDF (Windows Disk)
        ↓
SQL Server Engine
        ↓ (TCP 1433)
WSL (pgloader)
        ↓
PostgreSQL
