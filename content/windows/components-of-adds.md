### Logical
Partition - different parts of the AD database. Partitions can store copies on different DCs and then use replication to keep it synced. 

Schema - the definitions for the domain object types and attributes. 

domain - a logical container for objects such as computers, groups, users. Each domain maps to specific partition

domain tree - a heirarchal collection of domains that share a common higher level domain and a contiguousDNS namespace

forest - a collection of one or more domains that have a common AD DS root, schema or global catalog

OU - a conatainer object for objects that can be managed with group policy

container - organizational unit for AD DS stuff, cannot link to containers

### Physical
Domain controller  - stores a copy of the Database. usually can process and replicate changes to the domain

data store - a copy sits on each of the domain controllers

global catalog server - domain controller that hosts the global catalog, which is a partial read only copy of all the objects in a multiple domain forest. Speeds up the searching for objects in a different domain. 

Read Only DCs - a special form of domain controller that can only read and be replicated upon. They are not able to make changes to Domain settings. You may put these DCs in "risky areas" like a branch office or something. 
Somewhere with not great physical security or IT support

Site - where computers or users are physically located. Likeunto a domain which is a logical seperation, site is a physical seperation. 

subnet - portion of IP addresses given to a site. 


The three main objects of a domain are user accounts, computer accounts, and groups
