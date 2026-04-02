# pgloader Migration

## Goal

Migrate data from SQL Server to PostgreSQL.

---

## Install pgloader

```bash
sudo apt install -y pgloader
Migration Configuration

Create a file:

nano migrate.load
Config File
LOAD DATABASE
 FROM mssql://sa:password@xxx.xxx.xxx.xxx:1433/NightingaleHospitalDB
 INTO postgresql://postgres:password@localhost/nightingale_pg

WITH include drop, create tables, create indexes,
     reset sequences, foreign keys

CAST type uniqueidentifier to uuid using mssql-uniqueidentifier-to-uuid,
     type datetime        to timestamptz,
     type datetime2       to timestamptz,
     type tinyint         to smallint,
     type bit             to boolean;
Run Migration
pgloader migrate.load
Result
Tables migrated successfully
Data transferred without errors
Indexes and foreign keys created
Sequences reset correctly
Key Points
pgloader automatically converts schema and data
Handles datatype mapping between SQL Server and PostgreSQL
Enables fast and reliable migration
