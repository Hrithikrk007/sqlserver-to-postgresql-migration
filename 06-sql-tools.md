# Installing SQL Tools on WSL

## Required Packages

- msodbcsql18 → SQL Server driver
- mssql-tools18 → command-line tools (sqlcmd)

---

## Installation

```bash
sudo ACCEPT_EULA=Y apt install -y mssql-tools18 msodbcsql18

Add to PATH
echo 'export PATH="$PATH:/opt/mssql-tools18/bin"' >> ~/.bashrc
source ~/.bashrc
Test Connection
sqlcmd -S xxx.xxx.xxx.xxx,1433 -U sa -P 'YourPassword' -C \
 -Q "SELECT name FROM sys.databases"
