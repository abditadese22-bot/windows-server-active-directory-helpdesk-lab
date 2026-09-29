# Windows Server Active Directory Help Desk Lab

A hands-on Windows Server and Active Directory lab demonstrating practical IT support, identity administration, Windows domain management, Group Policy, DNS, and common help-desk tasks.

## Overview

This project simulates a small business Active Directory environment using Windows Server 2025 and Windows 11 in Oracle VirtualBox.

The lab was built to practice real-world IT support and system administration tasks including:

- Active Directory Domain Services (AD DS)

- DNS configuration

- Organizational Unit (OU) management

- User and security group administration

- Password resets

- Account disable, enable, and unlock operations

- Moving users between organizational units

- Windows domain joining

- Group Policy configuration and deployment

- Domain-user authentication

- PowerShell-based Active Directory administration

## Lab Environment

| Component | Configuration |

|---|---|

| Hypervisor | Oracle VirtualBox |

| Domain Controller | Windows Server 2025 Standard Evaluation |

| Domain Controller Name | DC01 |

| Client | Windows 11 Pro |

| Client Name | CLIENT01 |

| Active Directory Domain | abdi.lab |

| NetBIOS Domain | ABDI |

| DC01 IPv4 Address | 192.168.10.10 |

| CLIENT01 IPv4 Address | 192.168.10.20 |

| Network | VirtualBox Internal Network (ADLAB) |

| DNS Server | 192.168.10.10 |

## Active Directory Structure

The following Organizational Units were created:

- IT

- HR

- Finance

- Support

- Workstations

Test user accounts were created and organized by department:

| User | Username | Department |

|---|---|---|

| John Smith | jsmith | IT |

| Sarah Ahmed | sahmed | HR |

| David Wilson | dwilson | Finance |

| Michael Brown | mbrown | Support |

Department security groups were also created:

- IT-Staff

- HR-Staff

- Finance-Staff

- Support-Staff

Each test user was assigned to the appropriate security group.

## Help Desk Administration

Several common Active Directory help-desk operations were practiced using PowerShell:

- Resetting a user's password

- Requiring a password change at next logon

- Disabling a user account

- Re-enabling a user account

- Checking account lockout status

- Unlocking an account

- Moving users between Organizational Units

- Verifying user and group membership

These tasks simulate common identity and account-management requests handled by IT support teams.

## Windows 11 Domain Join

A Windows 11 Pro virtual machine named CLIENT01 was configured with:

- Static IPv4 address: 192.168.10.20

- DNS server: 192.168.10.10

- Internal VirtualBox network: ADLAB

Connectivity to the domain controller was verified before CLIENT01 was joined to:

abdi.lab

The CLIENT01 computer object was then moved into the Workstations OU.

A domain account was successfully used to authenticate to CLIENT01:

ABDI\jsmith

## Group Policy

A custom Group Policy Object named:

Workstation Security Policy

was created and linked to the Workstations OU.

The policy included:

- Machine inactivity limit: 900 seconds (15 minutes)

- Do not display the last signed-in username

After CLIENT01 was placed in the Workstations OU, Group Policy was refreshed using:

gpupdate /force

Policy application was verified using:

gpresult /scope computer /r

The results confirmed that both the Workstation Security Policy and Default Domain Policy were successfully applied to CLIENT01.

## Skills Demonstrated

- Windows Server administration

- Active Directory Domain Services

- DNS

- Windows 11 domain integration

- Organizational Units

- Active Directory users and groups

- Security group membership

- Account administration

- Password resets

- Account lockout troubleshooting

- Group Policy Management

- PowerShell

- TCP/IP configuration

- DNS troubleshooting

- VirtualBox networking

- Windows client/server troubleshooting

## Project Evidence

Screenshots in the screenshots directory document the lab configuration and successful testing, including:

- Active Directory users and security groups

- Organizational Unit structure
- CLIENT01 in the Workstations OU

- Group Policy configuration

- Workstation Security Policy settings

- Successful Group Policy application

- Domain-user authentication on CLIENT01

## What I Learned

This project strengthened my understanding of how Windows domains are deployed and administered in a practical IT support environment.

I gained hands-on experience managing users, groups, computers, password resets, account status, DNS, Group Policy, domain authentication, and Windows client/server communication.

Troubleshooting connectivity, DNS, domain membership, and Group Policy application also provided practical experience identifying and resolving common Windows support issues.

## Author

ABDI TADESE ALEMU

Built as part of my hands-on IT support, Windows administration, and cybersecurity portfolio.

