# SQL Server Configuration

## Goal
Allow SQL Server to accept connections from WSL (Linux)

---

## Steps

### 1. Enable TCP/IP

- Open SQL Server Configuration Manager
- Go to:
  SQL Server Network Configuration → Protocols for MSSQLSERVER
- Enable TCP/IP

---

### 2. Set Port 1433

- Open TCP/IP → Properties → IP Addresses
- In IPAll:
  - Clear TCP Dynamic Ports
  - Set TCP Port = 1433

---

### 3. Enable SQL Server Browser

- Start SQL Server Browser service
- Set startup type to Automatic

---

### 4. Enable Mixed Authentication

Run in SQL Server:

```sql
ALTER LOGIN aa ENABLE;
ALTER LOGIN aa WITH PASSWORD = 'XXXXXX';
