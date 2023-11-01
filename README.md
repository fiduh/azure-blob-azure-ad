# Azure Blob Storage and Azure AD

### Azure Blob Storage - is an Object store, used to store objects like videos, images, documents, files, etc.
It's accessible via HTTP/S, Client libraries for almost all programming languages exist for this. Data in Blob is encrypted by default

### Azure Blog Storage Structure:
You have the Azure Storage Account --> Below the Storage Account you have Containers (logical groupings of blobs) --> In the containers we upload the blobs themselves (Objects)

How do we add folders and files?

Create, Roles and Policies to restrict files for Users and Groups - Azure AD

How does a VM access a file stored in blob storage? - Add Roles to VMs

Users 

Joe 1 - has access to only test1 folder and sample1.json file

Joe 2 has access to only test 2 folder and sample2.json file

Create policies, roles, users, and groups

Joe 1 - From Virtual Machine, access file sample1.json stored in a blob storage

Joe 2- From Virtual Machine, access file sample2.json stored in a blob storage
