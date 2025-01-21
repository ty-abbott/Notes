AWS has availability zones and regions
- liken availability zones to a logical data center
- regions as sections of the world
- two or more availability zones in regions
- compliance requirements pay a hand in what regions are selected

Data center security
- housed in nondescript locations
- surveilance, security systems, alarms
- principle of least privilidge with access
- employee scrutinization

AWS Artifact
- no cost, compliance report self, service portal. SOC reports, PCI, eetc.

API calls
- everything that is done is through API calls on the management console

IAM
- Identity and authentication
- determines who has what level of access to your AWS system

Secrets Manager 
-AWS Secrets Manager is designed to centrally manage secrets used to access resources on AWS, on-premises, and third-party services. 
Secrets can be database credentials, passwords, third-party API keys, and even arbitrary text. With Secrets Manager, you can replace 
hardcoded credentials in your code with an API call to Secrets Manager to retrieve the secret programmatically. 
Also, you can configure Secrets Manager to automatically rotate the secret for you according to a schedule that you specify.

AWS STS
- The AWS Security Token Service (STS) is a web service that gives you the ability to request temporary, limited-privilege credentials
for IAM users who are taking on a different role, or for users who are being federated.

Directory Service
- AWS Directory Service for Microsoft Active Directory, also known as AWS Managed Microsoft AD, 
enables your domain workloads and AWS resources to use managed Active Directory in the AWS Cloud.
AWS Managed Microsoft AD is built on the actual Microsoft Active Directory and 
does not require you to synchronize or replicate data from your existing Active Directory to the cloud.

AWS organizations
- With AWS Organizations, you can centrally manage and enforce policies for multiple AWS accounts.
  This service allows grouping accounts into organizational units (OUs) and using service control policies to
  centrally control AWS services across multiple AWS accounts. With Organizations, you can automate the creation of new accounts through APIs.
 You can also streamline billing by setting up a single payment method for all the accounts in your organization through consolidated billing.
  Organizations is available to all AWS customers at no additional charge.

Amazon Cognito 
- With Amazon Cognito, you can add user sign-up, sign-in, and access controls to your web and mobile apps.
- You can define roles and map users to different roles so your app can access only the resources that are authorized for each user.
- User sign-in can be done either by a third-party identity provider, or directly through Amazon Cognito.
