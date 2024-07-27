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
