MMC can add the local group policy editor snap in which is how you can mess with group policy objects for workstations. This is how you can ensure srp and such usage


#### Default domain policy 
The Default Domain Policy GPO is linked to the domain, and it applies to Authenticated Users. This GPO doesn't have any WMI filters. Therefore, it affects all users and computers in the domain. This GPO contains policy settings that specify password, account lockout, and Kerberos version 5 authentication protocol policies.

These settings are of critical importance to the AD DS environment, and thus, make the Default Domain Policy a critical component of Group Policy. You shouldn't add unrelated policy settings to this GPO. If you need to configure other settings to apply broadly in your domain, create additional GPOs that link to the domain.

#### Default domain controllers policy

The Default Domain Controllers Policy GPO links to the OU of the domain controllers. Because computer accounts for domain controllers are kept exclusively in the Domain Controllers OU, and other computer accounts should be kept in other OUs, this GPO affects only domain controllers or other computer objects that are in the Domain Controllers OU.

You should modify GPOs linked to the Domain Controllers OU to implement your auditing policies and to assign user rights that are required on domain controllers.


#### Setting the domain password policy
this is found in the default domain policy, set it with navigating to 
Computer Configuration
Policies
Windows Settings
Security Settings
Account Policies
Password Policy

Then to deploy the domain policy do a:

From a command prompt with administrative permissions, type the following command:

gpupdate /force

What if you wanted to have different password policies for different people? The domain password policy sets the password policy for the entire domain. What if your organization wanted to have different password policies for different groups of people? Maybe vendors passwords need to require more frequent updates, domain admins need a more secure password, and other groups also need different password configurations.

A fine-grained password policy (FGPP) enables active directory to enforce different password policies for different groups.

Configure an FGPP
Open Active Directory Administrative Center (ADAC).
Expand the domain and click on the System container.
Locate the Password Settings Container.
Right-click on the Password Settings Container.
Select New and then Password Settings.
Configure the password requirements.
Select OK.
The FGPP is now created, and the procedure can be completed multiple times to create different variations or versions of an FGPP. Once the password settings object (PSO) is created, it needs to be associated with users or groups to be enforced.

Apply an FGPP
Still in the Password Settings Container, select the newly created PSO.
In the Extended view, under Direct Applies To, select Add.
Enter the name of the user or group and select OK.
This process can be repeated multiple times to create a more secure, customized domain that restricts access to maximize security and reduce the risk of compromised passwords.
