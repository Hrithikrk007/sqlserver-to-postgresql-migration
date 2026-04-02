This document presents the complete end-to-end implementation of a database migration 
from Microsoft SQL Server running on Windows to PostgreSQL running inside WSL2 
(Windows Subsystem for Linux).
> The source database, NightingaleHospitalDB, is a hospital clinical operations database containing 14 tables and 1036 rows covering wards, clinicians, 
admissions, procedures, supplies, equipment, and incident tracking. 
>The migration was carried out by first enabling TCP/IP connectivity on SQL Server, 
configuring Windows Firewall rules for the WSL2 subnet, installing Microsoft SQL tools on 
Linux, and finally running a pgloader migration script that automatically converted SQL 
Server data types to their PostgreSQL equivalents.
> The process was verified using both psql 
command-line tools and pgAdmin 4.

<img width="382" height="201" alt="Screenshot 2026-04-02 145201" src="https://github.com/user-attachments/assets/9e2fae43-bc97-4221-86e1-de697f32a38b" />
