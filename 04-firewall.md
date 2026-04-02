# Windows Firewall Configuration

## Problem

Even after enabling TCP/IP, SQL Server connections from WSL were blocked.

---

## Solution

Allow inbound traffic on port 1433 from the WSL network.

---

## Command Used

```powershell
New-NetFirewallRule -DisplayName "SQL Server 1433 WSL" `
  -Direction Inbound -Protocol TCP -LocalPort 1433 `
  -RemoteAddress IP/16 -Action Allow
