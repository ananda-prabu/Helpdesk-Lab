# Helpdesk-Lab (Windows Server 2025)

## 📌 Overview
This project demonstrates the deployment of a professional Ticketing System (osTicket) within a **WIMP Stack** environment. It simulates a real-world **Network Operations Center (NOC)** setup, focusing on identity management, role-based access control, and incident triage.

## 🛠 Tech Stack
- **OS:** Windows Server 2025 (Standard)
- **Web Server:** IIS 10.0
- **Database:** MySQL 8.x
- **Language:** PHP 8.2
- **Identity:** Active Directory Domain Services

## 🚀 Key Features & Implementation
### 1. Identity & RBAC
- Promotion of `Anand.local` Domain Controller.
- Implementation of **Role-Based Access Control (RBAC)** for Junior/Senior NOC staff.

### 2. Incident Simulation
- Configured automated ticket routing for Network Infrastructure (Core Switches) and Database clusters.
- **[Insert Screenshot of Dashboard Statistics here]**

## 🔧 Critical Troubleshooting: The LDAP/SQL Bypass
During implementation, an LDAP protocol mismatch was identified between osTicket and Windows Server 2025.
**Solution:** I performed a direct database intervention via MySQL to deactivate the faulty plugin:
```sql
UPDATE ost_plugin SET isactive=0 WHERE name='LDAP Authentication and Lookup';
