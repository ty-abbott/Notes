Rule of least privilidge is essentially everything 

https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/implementing-least-privilege-administrative-models

Credential manager is essentially a password manager built into windows, ensure that user accounts can not be a trusted caller

https://learn.microsoft.com/en-us/training/modules/manage-security-active-directory/2-configure-user-account-rights

https://www.tenable.com/blog/how-to-stop-the-kerberos-pre-authentication-attack-in-active-directory

https://jsecurity101.medium.com/ioc-differences-between-kerberoasting-and-as-rep-roasting-4ae179cdf9ec

Difference between kerberoasting and asrep roasting - kerberoasting requires a user account be compromised and pre authentication is on. Asrep preauthentication is off 
so initial domain compromise is not necessarily needed. As-rep gets a TGT where Kerberoasting gets a TGS ticket. TGT is used to request a TGS ticket. TGS is the actual service running kerberos authentication server. 
As rep roasting goes straight for the TGT because a TGT is not yet compromised and preauthentication is off. 

Deny logon as a service for user accounts. Only system and service accounts should be able to start or stop services without user interaction. We do not want normal user accounts the ability to create or start services. 

Delegate permissions to perform AD functions to users or groups, it is best practice to only give these permissions to groups. 

System Audit Policies
In Windows, a system audit policy, found under "Advanced Audit Policy Configuration," allows administrators to track and record security-related events on a system, enabling monitoring and analysis of activities that could impact security

Purpose:
System audit policies are a crucial part of security management, enabling administrators to monitor and analyze various security-related events. 


Location:
These policies are configured under "Advanced Audit Policy Configuration" within the Group Policy Management Editor (gpedit.msc). 


Categories:
Advanced audit policy settings are organized into categories, including:
Account Logon: Tracks authentication attempts. 
Account Management: Monitors changes to user and computer accounts. 
Detailed Tracking: Provides detailed information about user and application activities. 
DS Access: Audits Active Directory access and modifications. 
Logon/Logoff: Tracks logon and logoff events. 
Object Access: Monitors access to specific objects or types of objects. 
Privilege Use: Tracks the use of sensitive privileges. 
Policy Change: Monitors changes to security policies. 
System: Tracks system events. 
Global Object Access: Monitors access to global system objects. 


Auditing Events:
By configuring specific audit policy settings, administrators can choose which events to log, such as:
Successful and failed logon attempts. 
Changes to user accounts and groups. 
Access to files, folders, and registry keys. 
Changes to Active Directory. 
Changes to security policies. 


Benefits:
Enhanced Security: Enables administrators to detect and investigate security breaches or suspicious activities. 
Compliance: Helps organizations meet regulatory and industry compliance requirements. 
Troubleshooting: Provides valuable information for troubleshooting security-related issues. 
Forensic Analysis: Allows for the investigation of security incidents. 


Basic Audit Policy:
In addition to the advanced audit policy settings, there are basic audit policy settings under Security Settings\\Local Policies\\Audit Policy, which provide broad security audit capabilities for client devices and servers that can't use advanced security audit policy settings. 


Auditpol:
The auditpol command-line tool can be used to manage and query audit policies. 
