## Define Users, groups, and computers
In AD DS, you must provide all users that require access to network resources with a user account. 
With this user account, users can authenticate to the AD DS domain and access network resources.

A user account is an object that provides information that defines a user:
- username
- password
- groups the user is a member of

Managed Service accounts are used to run services on a server for an application.
Services typically run at service startup or are triggered by a specific event.
Services often run in the background and don't require any user interaction.
For a service to start up and authenticate, you use a service account.
A service account might be an account that is local to the computer, such as the built-in Local Service, Network Service, or Local System accounts. 
You also can configure a service account to use a domain-based account located in AD DS.

To help centralize administration and to meet program requirements, many organizations choose to use a domain-based account to run program services.
While this does provide some benefit over using a local account, there are a number of associated challenges, such as the following:
- Extra administration effort might be necessary to manage the service account password securely.
- It can be difficult to determine where a domain-based account is being used as a service account.
- Extra administration effort might be necessary to manage the service principal name (SPN).

Windows Server supports an AD DS object, named a managed service account, which you use to facilitate service-account management. 
A managed service account is an AD DS object class that enables:
- Simplified password management.
- Simplified SPN management.

Group managed service accounts
- basically takes managed acounts and goes one step further allowing the service account to be used on more than one server. 

Use cases for computer accounts
- A computer account in a domain is primarily used to authenticate and manage access to network resources for individual computers within a domain, allowing for centralized control over which computers can access shared files, printers, and other network services, while also enabling security policies to be applied based on the computer's identity and group memberships; essentially acting as a security principal for each device on the network.
- You must create a KDS root key on a domain controller in the domain for group managed service accounts to work

Group types
- security - Security groups are security-enabled, and you use them to assign permissions to various resources. You can use security groups in permission entries in access control lists (ACLs) to help control security for resource access. If you want to use a group to manage security, it must be a security group.
- distribution - Email applications typically use distribution groups, which are not security-enabled. You also can use security groups as a means of distribution for email applications.
