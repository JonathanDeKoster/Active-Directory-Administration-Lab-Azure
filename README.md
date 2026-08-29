# Active-Directory-Administration-Lab-Azure

## Overview

In this lab, I built and configured a basic Active Directory environment using Microsoft Azure and Windows Server.

The goal was to practice foundational Windows administration tasks commonly performed in IT support and system administration, including domain controller deployment, organizational units, user and group management, domain joining, authentication, password policies, and delegated administration.

---

## Objectives

- Deploy a Windows Server virtual machine in Microsoft Azure
- Install Active Directory Domain Services (AD DS)
- Promote the server to a domain controller
- Create an Active Directory domain
- Design a basic Organizational Unit (OU) structure
- Create and manage users
- Create and manage security groups
- Configure group membership
- Join a Windows client to the domain
- Authenticate as a domain user
- Configure a basic password policy
- Delegate password-reset permissions to a Help Desk group
- Move a domain computer into the appropriate OU
- Practice basic Active Directory troubleshooting

---

## Environment

| Component | Configuration |
|---|---|
| Cloud Platform | Microsoft Azure |
| Server OS | Windows Server |
| Client OS | Windows Server|
| Directory Service | Active Directory Domain Services |
| Domain | `lab.local` |
| Management Tools | Server Manager, Active Directory Users and Computers |
| Remote Access | Remote Desktop |

---

## Lab Architecture

The environment consisted of a Windows Server virtual machine acting as the domain controller and a Windows Server client joined to the domain.

```text
Microsoft Azure
│
├── Windows Server
│   └── Domain Controller
│       └── lab.local
│
└── Windows Server Client
    └── Joined to lab.local

```
---

## 1. Azure Virtual Machine Deployment

I deployed a Windows Server virtual machine in Microsoft Azure and connected to it using Remote Desktop Connection.



## 2.Installing Active Directory Domain Services

After connecting to the Windows Server, I used Server Manager to install the Active Directory Domain Services role.


After installation, the server was promoted to a domain controller and a new forest was created using:

lab.local

## 3. Active Directory Organizational Structure

I created basic OU structure to organize users and computers by branch and device type

lab.local
└── Branches
    └── [Grand Rapids]
        ├── Users
        ├── Workstations
        └── Laptops



This structure provides a logical foundation for managing users and computers and can be used for future Group Policy configuration


## 4. User Account Creation

I created several domain user accounts:

- Alice Johnson
- Bob Martinez
- Chris Walker


The accounts were created within the appropriate Users OU and verified through Active Directory Users and Computers


## 5. Security Groups

I created the following security groups: 
- Help Desk
- Accounting
- IT Support

Users were then assigned to the appropriate groups


This demonstrated how security groups can be used to organize users and control access to resources.



## 6. Joining the Windows Server Client to the Domain


The Windows Server client was configured to use the domain controller for DNS and then joined to the lab.local domain.


After restarting the client, I verified that the computer was successfully joined to the domain.



## 7. Domain Authentication

I logged into the Windows Server client using a domain user account


I then verified the authenticated user and group memberships from the client.


This confirmed that the client was communicating with the domain and that the user's domain group memberships were being recognized.



## 8. Password Policy

I configured a basic domain password policy and verified the resulting settings


This demonstrated how password requirements can be centrally managed through Active Directory.



## 9. Delegated Help Desk Administration

I delegated password-reset permissions on the User OU to the Help Desk security group.



This demonstrated how specific administrative tasks can be delegated to a Help Desk group without requiring full domain administrator privileges.



## 10. Computer OU Management

After joining the client to the domain, I moved the computer object into the appropriate branch OU.


This provides a foundation for applying computer-specific policies through Group Policy.


## 11. Skills Demonstrated

- Microsoft Azure VM Deployment
- Windows Server Administration
- Active Directory Domain Services
- Domain Controller configuration
- Active Directory Users and Computers
- Organizational Units (OUs)
- User Account administration
- Security Groups
- Group Membership
- Domain joining
- DNS configuration
- Domain authentication
- Password policies
- Delegated administration
- Windows client administration



## 12. What I Learned


This lab helped reinforce how several Windows infrastructure components work together:

- Active Directory provides centralized identity and user management.
- DNS is essential for domain communication and authentication.
- Organizational Units provide a logical structure for users and computers.
- Security groups can be used to organize users and control access.
- Group Policy provides centralized configuration and security management.
- Domain joining allows Windows clients to participate in the Active Directory environment.
- Administrative tasks can be delegated without granting unnecessary privileges.






