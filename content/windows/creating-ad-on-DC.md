### Creating the domain controller
- create using roles and groups by server manager
- on server core use powershell, or use RSAT
- interestingly you can also set up via a backup of another DC

### Updating the domain controller
- Upgrade the OS on existing domain controllers that are running Windows Server 2012 R2 or later.
- Add servers running Windows Server 2022 as domain controllers in a domain that already has domain controllers running earlier Windows Server versions.

### Migrating a domain controller to a new site

The first step of setting up the new location is creating a new site, so all of the computer, user, and other objects may be associated to the new location.

To create a new site in the Active Directory Sites and Services console:

Open the Active Directory Sites and Services console.
In the console tree, right-click Sites, and then select New Site.
Name the new site, associate it with the appropriate site link, and then click OK.
Alternatively, you can create a new site using the PowerShell command as follows.

To assign the newly created site to a subnet:

In the Active Directory Sites and Services console, expand the Sites folder to see the list of sites.
Right-click Subnets and select New Subnet.
Enter the subnet address and mask, and then select the site you created from the drop-down list.
Select OK to associate the subnet with your new site.
To use PowerShell to map a new site to a subnet, you can use the following command.

To move a domain controller to the new site:

In the Active Directory Sites and Services console, expand the site that currently contains the domain controller you want to move.
Expand the Servers folder, and then expand the server that represents the domain controller.
Right-click the domain controller's NTDS Settings object, and then select Move.
In the Move Server dialog box, select the new site to which you want to move the domain controller, and then select OK.
Just as you can use PowerShell to create a new site and map it to a subnet, you can use PowerShell to move a domain controller.

