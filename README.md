# Active-Directory-Deployment-Hardening - Secure domain controller with baseline GPOs

# Active Directory Simulation – CyberTech AI Solutions

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **CyberTech Solutions**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**CyberTech Solutions** is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8 A Client PC (IT Department)
- 1 x Windows 8 B Client PC (Sales Department)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.2.1)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8 A)   PC2 (Win 8 B)
```

| Device        | IP Address      | Role                        |
|---------------|----------------|-----------------------------|
| Windows Server| 10.0.2.15  | AD Domain Controller (DC)   |
| Windows 8 A PC  | DHCP    | Client (IT)           |
| Windows 8 B PC | DHCP    | Client (Sales)        |

---

## Domain Configuration

- **Domain Name**: `cybertech.ai`
- **Server Name**: `CYBERTECH`
- **Static IP**: `10.0.2.15`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
CyberTech.local
├── OU: IT Department
│   └── Users: Sam.IT
    └── Users: JAy.IT

├── OU: Sales
│   └── Users:
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `DisableaccesstoCMD`and `Disableshutdownability`
- **Linked to**: OU: IT Department
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `System` > `Disable access to CMD`
  - Set **"All Removable Storage classes: Deny all access"** to **Enabled**

Result: CMD access is disabled for all users in the **Sales OU**.

---

## Screenshots

- AD Domain Structure
- GPO Editor Screenshot
- PC joined to domain
- Disable access to CMD

---

## Key Takeaways

- Gained practical experience with Windows Server roles and domain setup
- Implemented centralized access control using Group Policy
- Learned how to structure users and departments with OUs
- Applied IAM concepts in a real-world simulated environment

---

## Author

**Temitayo Olanrewaju**  
Cybersecurity Analyst  

