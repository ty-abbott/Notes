Anonymous logon is triggered any time that there is a connection to a server or machine without authentication. This can be a very legitimate usage if there is a public resource such as a ftp server or iis server. Depending on the resource perhaps authentication should be used

NT Authority is the name of predefined account or groups that are part of the operating system functionality. so when we see that we know that the permission or privilege is being granted to one of these accounts

It can be disabled through the registery to use the guest account instead but hardening that account is still necessary

Misconfig of acccess controls can happen such as with policy setting requiring logged in user but if the anonymous logon group explicitely has permissions to access resources then that will allow them to still access  

There are a variety of different things that the account/s can access - shares and other databases. 

there are a few controls that we for sure want to set for anonymous account
- Ensure that anonymous logon group isn’t a member of the Everyone group by default aka the logged users 
- Limit access (through remote procedure calls) to and enumeration of security accounts in the security accounts manager (SAM) or the database that contains the local usernames and passwords. 
- Disable null session pipes or restrict anonymous connections by not allowing anonymous SID/names in access tokens.

Important information with this 
- Remote procedure calls (RPC) are used to communicate with the system whether it be local or on a different computer https://en.wikipedia.org/wiki/Remote_procedure_call
- pipes are used for interprocess communication. it is a server to client communication. There can be multiple instances of the same pipe but each has their own buffers and function https://learn.microsoft.com/en-us/windows/win32/ipc/pipes


