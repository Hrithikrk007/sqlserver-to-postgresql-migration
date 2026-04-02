# Errors and Resolutions

## 1. Wrong Configuration Manager Node

**Problem:** Selected 32-bit configuration node  
**Fix:** Use correct "SQL Server Network Configuration"

---

## 2. Connection Refused

**Problem:** Used incorrect IP  
**Fix:** Use Windows host gateway instead of DNS IP

---

## 3. pgloader Syntax Error

**Problem:** Unsupported syntax in config  
**Fix:** Removed incompatible clause

---

## 4. text(n) Error

**Problem:** PostgreSQL does not allow length on text  
**Fix:** Removed nvarchar → text cast

---

## 5. Missing Semicolon

**Problem:** pgloader requires semicolon  
**Fix:** Added ; at end of config

---

## 6. Database Not Visible in pgAdmin

**Problem:** Different PostgreSQL instances  
**Fix:** Exposed WSL PostgreSQL and connected via IP
