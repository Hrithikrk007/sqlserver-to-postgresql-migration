# PostgreSQL Setup in WSL

## Goal

Prepare PostgreSQL in WSL to receive migrated data.

---

## Start PostgreSQL Service

```bash
sudo service postgresql start
Create Target Database
sudo -u postgres psql -c "CREATE DATABASE nightingale_pg;"
Set Password for postgres User
sudo -u postgres psql -c "ALTER USER postgres PASSWORD 'yourpassword';"
Why this is required
PostgreSQL must be running before migration
pgloader requires an existing target database
Password is needed for external tools like pgAdmin
Result
PostgreSQL service started successfully
Target database created
Authentication configured

---

👉 Commit this

---

# 🎯 What this step shows

You’re demonstrating:
- Linux service management
- DB setup before migration
- Understanding of pgloader requirements
