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

### Azure AD (Active Directory) 
Cloud-based Central identity and access management service. 

Create, Roles and Policies to restrict files for Users and Groups - Azure AD

How does a VM access a file stored in blob storage? - Add Roles to VMs

Users 

Joe 1 - has access to only test1 folder and sample1.json file

Joe 2 has access to only test 2 folder and sample2.json file

Create policies, roles, users, and groups

Joe 1 - From Virtual Machine, access file sample1.json stored in a blob storage

Joe 2- From Virtual Machine, access file sample2.json stored in a blob storage
