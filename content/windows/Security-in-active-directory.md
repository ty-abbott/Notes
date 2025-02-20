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
