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


## 2. Installing Active Directory Domain Services

After connecting to the Windows Server, I used Server Manager to install the Active Directory Domain Services role.


After installation, the server was promoted to a domain controller and a new forest was created using:

- lab.local

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
- Troubleshooting Active Directory requires understanding how identity, DNS, authentication, group membership and policies interact.



## 13. Screenshots


## Azure Infrastructure

<img width="2553" height="1313" alt="01-azure-vm" src="https://github.com/user-attachments/assets/e420ec71-8828-4cbf-b1fe-c50c4605f1f3" />
<img width="2558" height="1321" alt="02-dc-network-settings" src="https://github.com/user-attachments/assets/3b3a7976-ac8f-49fb-a6cc-0a7336140153" />
<img width="2559" height="1316" alt="03-dc-static-ip" src="https://github.com/user-attachments/assets/72f96dc5-92a4-4781-acc6-73304783634f" />
<img width="2556" height="1468" alt="13-client-vm" src="https://github.com/user-attachments/assets/5d7ac41d-09f8-40f1-a09e-f2a061ffc9c2" />


## Domain Controller & Active Directory Configuration
<img width="2554" height="1536" alt="05-server-manager" src="https://github.com/user-attachments/assets/3c0f1813-a536-45b8-91d9-e65a3caa5251" />
<img width="2366" height="1423" alt="06-add-ad-ds" src="https://github.com/user-attachments/assets/9a59d195-0476-4ba5-a180-1b6472b4e2a4" />
<img width="2363" height="1415" alt="07-promote-domain-controller" src="https://github.com/user-attachments/assets/d4a3a675-f12a-4114-b564-01c9f592b7b8" />
<img width="2359" height="1407" alt="09-ou-structure" src="https://github.com/user-attachments/assets/87d94894-e8bd-49d5-bc4a-2b14f6ab466f" />


## Users, Groups & Administration
<img width="2359" height="1416" alt="10-ad-users" src="https://github.com/user-attachments/assets/5a6ac67d-bc55-481e-b1a3-734f1c7b855c" />
<img width="2360" height="1418" alt="11-ad-groups" src="https://github.com/user-attachments/assets/1a192b3e-6668-4bbd-acc4-05ad95784e68" />
<img width="2350" height="1413" alt="12-helpdesk-membership" src="https://github.com/user-attachments/assets/8c4ca1ae-41ce-4070-891e-a1acaf7f5ede" />
<img width="1181" height="709" alt="21-new-password-policy" src="https://github.com/user-attachments/assets/c663acac-515c-40a2-be5c-3439502ee14c" />
<img width="1179" height="710" alt="22-delegation-wizard" src="https://github.com/user-attachments/assets/226ac961-c9aa-4c6c-8548-8090f64a89bb" />


## Domain Client & Authentication
<img width="2350" height="1412" alt="14-client-domain-join" src="https://github.com/user-attachments/assets/b4968f5b-ab77-4e8f-8699-4fa1648455e9" />

<img width="2357" height="1423" alt="15-client-domain-join-success" src="https://github.com/user-attachments/assets/10872000-54a2-4318-bd1a-a79d0d45da8b" />

<img width="1182" height="708" alt="16-client-in-ad" src="https://github.com/user-attachments/assets/410ab155-140b-4d62-a056-5bc3fc69edb5" />

<img width="1179" height="704" alt="17-remote-desktop-groups" src="https://github.com/user-attachments/assets/22bdd90a-a749-45ed-8172-5055430230ec" />



