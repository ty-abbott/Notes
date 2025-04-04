When a user is a member of the Protected Users group, on their workstation or local device:

User credentials aren't cached locally.
Credential delegation (CredSSP) won't cache user credentials.
Windows Digest will not cache user credentials.
NTLM won't cache user credentials.
Kerberos won't create DES (Data Encryption Standard) or RC4 keys, or cache credentials or long-term keys.
The user can no longer sign-in offline.

On domain controllers running Windows Server 2012 R2 or later:

NTLM authentication isn't allowed.
DES and RC4 encryption in Kerberos pre-authentication can't be used.
Credentials can't be delegated using constrained delegation.
Can't be delegated using unconstrained delegation.
Ticket-granting tickets (TGTs) can't renew past the initial lifetime.

Authentication policy silos allow administrators to assign authentication policies to user, computer, and service accounts. Authentication policy silos work with the Protected Users group to add configurable restrictions to the group’s existing non-configurable restrictions. In addition, policy silos ensure that the accounts belong to only a single authentication policy silo.

When an account signs in, a user that is part of an Authentication policy silo is granted an Authentication Policy Silo claim. This silo claim controls access to claims-aware resources to verify whether the account is authorized to access that device. For example, you might associate accounts that can access sensitive servers with a specific Authentication policy silo.
