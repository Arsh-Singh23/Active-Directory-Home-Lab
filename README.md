# Active Directory Home Lab — Windows Server 2022

## Overview
A self-directed home lab simulating a real enterprise Active Directory environment using VirtualBox and Windows Server 2022. This lab covers domain controller setup, organizational unit design, user and group management, and Group Policy configuration — core skills required for IT Support, Service Desk, and Systems Administration roles.

---

## Environment
| Component | Details |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2022 |
| Domain Name | arshjot.local |
| Lab Type | Self-directed / Home Lab |

---

## What Was Built

### 1. Domain Controller Setup
- Installed Windows Server 2022 on a VirtualBox VM
- Installed the Active Directory Domain Services (AD DS) role
- Promoted the server to a Domain Controller
- Configured domain: `arshjot.local`

### 2. Organizational Units (OUs)
Created 3 OUs to reflect a real enterprise department structure:
- `IT`
- `HR`
- `Finance`

### 3. Users
Created 6 users across the 3 departments:

| Username | Full Name | OU | Role |
|---|---|---|---|
| a.johnson | Alice Johnson | IT | IT Admin |
| b.smith | Bob Smith | IT | IT Support |
| c.white | Carol White | HR | HR Manager |
| d.brown | David Brown | HR | HR Coordinator |
| e.davis | Emma Davis | Finance | Finance Analyst |
| f.lee | Frank Lee | Finance | Finance Manager |

### 4. Security Groups
Created 3 Global Security Groups following enterprise best practices:

| Group | OU | Members |
|---|---|---|
| GRP_IT | IT | a.johnson, b.smith |
| GRP_HR | HR | c.white, d.brown |
| GRP_Finance | Finance | e.davis, f.lee |

### 5. Group Policy Objects (GPOs)
Created and linked 3 GPOs simulating real enterprise security policies:

| GPO Name | Linked To | Policy Applied |
|---|---|---|
| GPO_PasswordPolicy | arshjot.local (domain-wide) | Minimum 10 character passwords, complexity enabled, 90 day expiry |
| GPO_ScreenLock | IT OU | Screen saver enabled, 10 minute timeout, password protected |
| GPO_RestrictControlPanel | HR OU | Control Panel and PC Settings access prohibited |

---

## Key Concepts Demonstrated
- Active Directory domain controller promotion and configuration
- Organizational Unit design reflecting real enterprise department structure
- User lifecycle management — creation, group assignment, and account administration
- Role-based access control through Global Security Groups
- Group Policy design and OU-level policy linking
- Least-privilege access principles applied through RBAC and GPO restrictions

---

## Status
- [x] Domain Controller setup
- [x] Organizational Units created
- [x] Users created
- [x] Security Groups created and populated
- [x] GPOs created and linked
- [ ] Windows 10 client VM joined to domain *(in progress)*

---

## Next Steps
- Join a Windows 10 client VM to arshjot.local domain
- Verify GPO application on client machine using `gpresult /r`
- Document screenshots of each configuration step
- Connect to Lab 05 — Hybrid AD + Entra ID Connect

---

## Related Labs
- [Lab 01 — Azure Entra ID IAM Lab](https://github.com/Arsh-Singh23/Azure-Entra-ID-IAM-Lab)
