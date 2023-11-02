# Azure Blob Storage and Azure AD

### Azure Blob Storage - is an Object store, used to store objects like videos, images, documents, files, etc.
It's accessible via HTTP/S, Client libraries for almost all programming languages exist for this. Data in Blob is encrypted by default

How do we add folders and files?

### Azure Blob Storage Structure:
You have the Azure Storage Account --> Below the Storage Account you have Containers (logical groupings of blobs) --> In the containers we upload the blobs themselves (Objects)

### Azure Blob Storage Redundancy Options - there are six options available.
LRS - Locally Redundant Storage (Data is synchronously copied 3 times within the same zone

ZRS - Zone Redundant Storage ( Data is synchronously copied to 3 Zones in the Region)

GRS - Geo Redundant Storage (Data is synchronously copied 3 times within the same zone, and then copied asynchronously to paired Region. Data in the secondary Region is accessible only after Failover process)

GZRS - Geo-Zone Redundant Storage (Data is synchronously copied to 3 zones in the Region, and then copied asynchronously to paired Region. Data in the secondary Region is accessible only after Failover process) 

RA-GRS - Read Access-Geo Redundant Storage (Data is synchronously copied 3 times within the same zone, and then copied asynchronously to paired Region. There's a read-access to the data in the secondary Region) 

RA-GZRS - Read Access-Geo-Zone Redundant Storage (Data is synchronously copied to 3 zones within the same Region, and then copied asynchronously to paired Region. There's a read-access to data in the secondary Region)

### Azure Blob Storage Tiers - Blobs are uploaded to one of three tiers 
Hot - Data that are accessed frequently, Best SLA (99.9%), Highest storage costs, Lowest access costs, Examples (Photos and Documents to show)

Cool - Data that are accessed infrequently, Slightly lower SLA (99%), Lower storage cost, Higher access costs, Must be stored for at least 30 days (or early deletion fees applied), Example (Short term backup, Data for future processing)

Archive - Data for archival, Stored offline, no SLA, can take hours to retrieve, Lowest storage costs, Highest access costs, Must be stored for at least 180 days (or early deletion fees applied) 

### Microsoft Entra ID (Formerly Azure Active Directory) 
Cloud-based Central identity and access management service. 

### Azure AD Tenant - an instance of Azure Active Directory
Each Azure AD tenant is distinct and separate from other Azure AD tenants.
Tenant contains Users, Groups, Devices, Apps - they are all grouped with each other under that tenant 

### Role-Based Access Control (RBAC)
Allows you to delegate access to manage your cloud resources, so you don't have to provide access to your entire Azure subscription and potentially compromise a whole lot of different assets, instead if a particular person only needs access to certain specific services or specific resources inside of your azure subscription to perform their job role, you can create a role that has those permissions defined and then provide that person access to the role.

### Role - a collection of actions that the assigned identity will be able to perform.
Role definition is an answer to a question "What can be done?" 

A role needs to be assigned to an identity (Security Principal - these are objects within Active Directory that represents users or applications, those could be users or groups of users, application accounts) 

### Security Principal - an Azure object (identity) that can be assigned to a role (ex. users,groups or applications)
Security Principal assignment is an answer to the question "Who can do it?" 
Create a User, attach a Reader role to it at the subscription level, attach a Storage owner role to it at the Container level, and Repeat for the second user.

Create, Roles and Policies to restrict files for Users and Groups - Azure AD

How does a VM access a file stored in blob storage? - Add Roles to VMs

Users 

Joe 1 - has access to only test1 folder and sample1.json file

Joe 2 has access to only test2 folder and sample2.json file

Create policies, roles, users, and groups

Joe 1 - From Virtual Machine, access file sample1.json stored in a blob storage

Joe 2- From Virtual Machine, access file sample2.json stored in a blob storage
