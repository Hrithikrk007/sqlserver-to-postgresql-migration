# pgAdmin Setup and Verification

## Problem

PostgreSQL running in WSL is not visible in pgAdmin on Windows by default.

---

## Solution

Expose PostgreSQL from WSL to allow external connections.

---

## Configuration Changes

### 1. Update postgresql.conf

```bash
sudo nano /etc/postgresql/*/main/postgresql.conf
Change:

listen_addresses = '*'
2. Update pg_hba.conf
sudo nano /etc/postgresql/*/main/pg_hba.conf

Add:

host all all 0.0.0.0/0 md5
3. Restart PostgreSQL
sudo service postgresql restart
Connect via pgAdmin

Use:

Host: xxx.xxx.xxx.xxx
Port: 5432
Username: postgres
Password: yourpassword
Result
PostgreSQL from WSL visible in pgAdmin
Database nightingale_pg accessible
All tables successfully displayed
