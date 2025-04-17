There are two reasons to create an OU:

To consolidate objects to make it easier to manage them by applying GPOs to the collective. When you assign GPOs to an OU, the settings apply to all the objects within the OU. GPOs are policies that administrators create to manage and configure settings for computers or users. You deploy the GPOs by linking them to OUs, domains, or sites.
To delegate administrative control of objects within the OU. You can assign management permissions on an OU, thereby delegating control of that OU to a user or a group within AD DS, in addition to the Domain Admins group.
You can use OUs to represent the hierarchical, logical structures within your organization. For example, you can create OUs that represent the departments within your organization, the geographic regions within your organization, or a combination of both departmental and geographic regions. You can use OUs to manage the configuration and use of user, group, and computer accounts based on your organizational model.

AD DS has several built-in containers, or generic containers, such as Users and Computers. 
These containers store system objects or function as the default parent objects to new objects that you create.
Don't confuse these generic container objects with OUs. The primary difference between OUs and containers is the management capabilities. 
Containers have limited management capabilities. For example, you can't apply a GPO directly to a container.

Installing AD DS creates the Domain Controllers OU and several generic container objects by default. AD DS primarily uses some of these default objects, which are also hidden by default. The following objects are displayed by default:

Domain. The top level of the domain organizational hierarchy.
Builtin container. A container that stores several default groups.
Computers container. The default location for new computer accounts that you create in the domain.
Foreign Security Principals container. The default location for trusted objects from domains outside the local AD DS domain that you add to a group in the local AD DS domain.
Managed Service Accounts container. The default location for managed service accounts. AD DS provides automatic password management in managed service accounts.
Users container. The default location for new user accounts and groups that you create in the domain. The Users container also holds the administrator, the guest accounts for the domain, and some default groups.
Domain Controllers OU. The default location for domain controllers' computer accounts. This is the only OU that is present in a new installation of AD DS.

The administrative needs of the organization dictate the design of an OU hierarchy. Geographic, functional, resource, or user classifications could all influence the design. Whatever the order, the hierarchy should make it possible to administer AD DS resources as effectively and flexibly as possible. For example, if you need to configure all IT administrators’ computers in a certain way, you can group all the computers in an OU and then assign a GPO to manage those computers.

You also can create OUs within other OUs. For example, your organization might have multiple offices, each with its own IT administrator who is responsible for managing user and computer accounts. In addition, each office might have different departments with different computer-configuration requirements. In this situation, you can create an OU for each office, and then within each of those OUs, create an OU for the IT administrators and an OU for each of the other departments.

Although there's no limit to the number of levels in your OU structure, limit your OU structure to a depth of no more than 10 levels to ensure manageability. Most organizations use five levels or fewer to simplify administration.
