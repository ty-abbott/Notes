While NTLM hashes provide a level of security by not storing plaintext passwords, the way these hashes are managed can be exploited.

When a user logs into a machine, LSASS handles the authentication process and stores the user’s NTLM hash into system memory. You can extract these hashes from Local Security Authority Subsystem Service (LSASS) memory and inject them back into the system through a system call to impersonate the user. In remote attacks, tools like PsExec exploit services like SMB, which are designed to accept a hash instead of a password for authentication.

This makes LSASS a prime target to exploit NTLM hashes from to use in a pass-the-hash attack.

MIMIKATZ needs admin creds to work

when you get hash' check the SID to see what groups and whatnot they are in. 

Utilize psexec or something else to laterally move 
