## NTLM assesment

### Finding systems/apps/services that use NTLM
- a siem or log analysis obviously can be used to search for NTLM auth
- you can also audit with https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/security-policy-settings/network-security-restrict-ntlm-ntlm-authentication-in-this-domain  Network Security: Restrict NTLM: Audit NTLM authentication in this domain - this is what it is called . 

https://learn.microsoft.com/en-us/troubleshoot/windows-server/windows-security/audit-domain-controller-ntlmv1 

Sometimes legacy servers or applications require NTLM for authentication and functionality. In these situations where it is necessary it is critical to be using NTLMv2. Phase out of NTLM v1 using network authentication protocol settings in security policies. The goal would be level 5, force NTLMv2 with no downgrade. 

Since integrity checks with NTLM are not implemented by default then a control to ensure that the NTLM challenge and responses are actually from the intended client and servers is required. SMB signing is helppful for that. 

Since the authentication protocol with challege and responses are in plain text. EPA is helpful to tunnel it. 

NTLM relay attacks - taking the response and then presenting it to the server and essentially taking that authentication. 

Password cracking is a risk, if passwords are weak then they will be cracked. 

### How to deny 
After you have determined that you can block NTLM in your organization, you need to configure the Restrict NTLM: NTLM authentication in this domain policy in the previous Group Policy node. The configuration options are:

Deny for domain accounts to domain servers. This option denies all NTLM authentication sign-in attempts for all servers in the domain that use domain accounts, unless the server name is listed in the Network Security: Restrict NTLM: Add server exceptions for NTLM authentication setting in this domain policy.
Deny for domain accounts. This option denies all NTLM authentication attempts for domain accounts unless the server name is listed in the Network Security: Restrict NTLM: Add server exceptions for NTLM authentication setting in this domain policy.
Deny for domain servers. This option denies NTLM authentication requests to all servers in the domain unless the server name is listed in the Network Security: Restrict NTLM: Add server exceptions setting for NTLM authentication in this domain policy.
Deny all. This option ensures that all NTLM pass-through authentication requests for servers and accounts will be denied unless the server name is listed in the Network Security: Restrict NTLM: Add server exceptions setting for NTLM authentication in this domain policy.
To disable NTLM on domain controllers using the Group Policy Management Console, you can follow these steps:

Open the Group Policy Management Console (GPMC).
Create a new Group Policy Object (GPO) and give it a descriptive name.
Edit the GPO and navigate to Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options.
Locate the policy Network security: Restrict NTLM: NTLM authentication in this domain and set it to Deny all.
Locate the policy Network security: Restrict NTLM: Add server exceptions in this domain and configure it with the necessary exceptions if required.
Link the GPO to the domain controllers’ Organizational Unit (OU).
Ensure the policy is enforced by running the gpupdate /force command on the domain controllers or waiting for the next Group Policy refresh cycle.

