# 🧩 TryHackMe – Active Directory Basics

## 📘 Room Information
- **Path:** Pre-Security → Windows Fundamentals → Active Directory Basics  
- **Difficulty:** Easy  
- **Completed on:** 2025-05-15  
- **Room Link:** [TryHackMe – Windows Fundamentals Part 3](https://tryhackme.com/room/winadbasics)

---

> ⚠️ **Disclaimer:**  
> This write-up is for educational and documentation purposes only. It does not include flags or exact solutions, in line with [TryHackMe’s Terms of Use](https://tryhackme.com/terms).

---

## 🔍 Room Overview
This room is about learning about Active Directory. Things such as:
- What Active Directory is
- What an Active Directory Domain is
- What components go into an Active Directory Domain
- Forests and Domain Trust

**Tasks:**
1. Introduction  
2. Windows Domains  
3. Active Directory  
4. Managing Users in AD  
5. Managing Computers in AD  
6. Group Policies  
7. Authentication Methods  
8. Trees, Forests and Trusts  
9. Conclusion  

---

## 📂 Room Walkthrough

### 🔹 Task 1 – Introduction
- Quick overview of what the room will cover.

---

### 🔹 Task 2 - Windows Domains
- A Windows Domain helps manage many computers from a central place.
- It groups users and computers under one organization using Active Directory (AD).
- A **Domain Controller (DC)** is the server running AD services.

#### Benefits:
- Central management of users and computers.
- Security policies can be applied from one place.

#### Example:
- In schools or universities, you log in with one username on any computer — your credentials are checked by the AD.

---

### 🔹 Task 3 - Active Directory
**Active Directory Domain Services (AD DS)** is the heart of a Windows Domain. It stores info about objects like users, computers, and groups.

#### Objects:

**Users**
- These are accounts for people or services.
- They can log in and access resources.

**Machines**
- When a computer joins a domain, a machine object is created.
- Machine accounts are like users but usually not used by people.

**Security Groups**
- Groups of users/machines that can share permissions.
- Examples:
  - Domain Admins → control the whole domain
  - Backup Operators → access any file to perform backups
  - Domain Users → all normal users
  - Domain Computers → all joined machines

#### Organizational Units (OUs)
- Containers used to group users/computers logically.
- Helps apply different policies to different departments.
- A user can only be in one OU.

#### Default Containers:
- Builtin → default groups
- Computers → new machines join here
- Domain Controllers → contains DCs
- Users → default user/group accounts
- Managed Service Accounts → for services

#### Security Groups vs OUs
| Feature | Security Groups | OUs |
|--------|-----------------|-----|
| Purpose | Manage permissions | Apply policies |
| Members | Users, machines | One per user/machine |
| Multiple Memberships | Yes | No |

---

### 🔹 Task 4 - Managing Users in AD

**OUs are protected** from accidental deletion. To disable:
- Enable "Advanced Features" in the "View" menu.
- Right-click OU → Properties → Uncheck deletion protection.

#### Delegation
- Lets specific users manage OUs without being Domain Admins.
- Example: Let IT Support reset user passwords.

Steps:
1. Right-click OU → Delegate Control
2. Add user
3. Select task: reset user passwords

#### Reset Password via PowerShell
```powershell
Set-ADAccountPassword name -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
```

### 🔹 Task 5 - Managing Computers in AD

- All machines that join the domain are placed in the "Computers" container by default.
- It’s better to organize devices into different OUs for easier management and policy assignment.

#### Recommended Categories:
- **Workstations**: Devices used by end users.
- **Servers**: Machines providing services.
- **Domain Controllers**: Critical machines holding hashed passwords and managing the AD.

- **Task**: Create two separate OUs to organize computers properly.

---

### 🔹 Task 6 - Group Policies

- Group Policy Objects (GPOs) let admins configure settings and enforce security on users and computers.
- GPOs can be linked to specific OUs.

#### Group Policy Management:
- Open the Group Policy Management tool.
- GPOs are created under "Group Policy Objects" and then linked to target OUs.

**GPO Tabs:**
- **Scope**: Shows where the GPO is linked. Security Filtering allows you to target specific users/computers.
- **Settings**: Shows what the GPO does (User vs Computer configurations).

- GPOs are stored in `C:\Windows\SYSVOL\sysvol\` on Domain Controllers.
- To sync GPOs immediately: `gpupdate /force`

#### Practical Tasks:

**Block Control Panel for Non-IT Users**
- Create GPO.
- Go to **User Configuration** → Find the Control Panel policy and enable it.
- Link GPO to non-IT user OUs.

**Auto-Lock Screen after 5 Minutes**
- Create GPO.
- Go to **Computer Configuration** → Enable the policy for auto-lock.
- Link it to the root domain so all computers inherit it.

---

### 🔹 Task 7 - Authentication Methods

When using AD, credentials are stored on Domain Controllers. Services use the DC to verify user logins.

#### Protocols:
- **Kerberos** (default)
- **NetNTLM**

##### Kerberos Process:
1. User sends their username + encrypted timestamp to the Key Distribution Center (KDC).
2. KDC sends back a Ticket Granting Ticket (TGT) + Session Key.
3. User uses TGT to request a Ticket Granting Service (TGS) to access a specific service.
4. TGS is used to authenticate with the service.

##### NetNTLM Process:
1. Client sends login request to server.
2. Server sends random challenge.
3. Client encrypts challenge with password hash and sends it back.
4. Server sends response to DC.
5. DC verifies it and sends back result.
6. Server allows or denies access.

---
### 🔹 Task 8 - Trees, Forests, and Trusts

#### Trees
- Useful when a company grows and needs to separate administration (e.g., different countries).
- Trees are domains that share the same namespace (e.g., `corp.local`, `at.corp.local`, `us.corp.local`).
- Each domain in the tree has its own Domain Controller and can apply its own policies.
- Introduces the **Enterprise Admins** group: can manage all domains in the tree.
- **Domain Admins**: can manage only their own domain.

#### Forests
- When companies with **different namespaces** are joined together (e.g., `corp.local` and `newcompany.local`), they form a **forest**.
- Each tree keeps its structure, but they’re linked under one umbrella (the forest).
- Forests allow broader collaboration while maintaining separate management.

#### Trust Relationships
- Trusts let users from one domain access resources in another.

**Types:**
- **One-Way Trust**: Domain A trusts B = B can access A, but not the other way around.
- **Two-Way Trust**: Both domains trust each other = mutual access possible.

- Trust ≠ automatic access. Permissions still have to be granted explicitly.

---

### 🔹 Task 9 - Conclusion

- This room introduced key Active Directory concepts:
  - Domains and Domain Controllers
  - Users, Machines, Security Groups, and Organizational Units
  - Delegation and user management
  - Group Policies and their scope
  - Kerberos and NetNTLM authentication
  - Domain structures with Trees, Forests, and Trusts

- These basics are essential to understanding how corporate Windows environments are structured and secured.

---
