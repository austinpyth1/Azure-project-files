# Guide to Deploying a Secure, Highly Available Virtual Machine (VM) in Azure

## Objectives
- Set up an Azure Storage Account in Microsoft Azure.
- Create a blob container for file storage.
- Upload and download files using Azure.

## Skills Learned
- Cloud storage management.
- Understanding data redundancy options in Azure.

## Technologies Used
- Azure Storage Account.
- Blob Storage.


## Description
This project demonstrates how to create and manage an Azure Storage Account and Blob containers using Azure. It includes step-by-step instructions for setting up the account, creating a blob container, and managing files.
Tools Used
1. Azure Portal
Used to create and manage Linux Web App.
2. Azure storage
3. Containers




## Steps
- Log in to the Azure Portal:
Go to the Azure Portal and sign in with your credentials.
- Create a New Storage Account:
In the left-hand menu, click on Storage accounts or search for "Storage accounts" in the search bar.
Click on Create to start the creation process.
- Set Storage Account Details:
Resource group: Select an existing resource group or create a new one.
Storage account name: Enter a unique name for your storage account. This must be globally unique because it's used for the URL 
Region: Choose the location.
Performance: Select between Standard (cost-effective) or Premium (higher performance, higher cost).
Redundancy: Choose the replication option (e.g., Locally-redundant storage (LRS) for simple redundancy within a region)
![Screenshot (67)](https://github.com/user-attachments/assets/59d679b0-c22c-4102-ae9b-2c51b5475292)
On the Advanced tab of the Create a storage account blade, Allow enabling anonymous access on individual containers  Leave the defaults for everything else.
![Screenshot (68)](https://github.com/user-attachments/assets/f821602c-c093-43de-8a7d-4601dc35194d)
- Select Review and Create to make your new blob storage
  ## Work with blob storage
- click on upload then create a new container
- set the access level to public and allow anonymous user to view
![Screenshot (70)](https://github.com/user-attachments/assets/4b6feafc-508d-4700-9604-9ad86a2c3521)
![Screenshot (71)](https://github.com/user-attachments/assets/15042201-1cdc-44b0-8499-108caf9b3885)

 - click on the new container and then upload a new blob to it
 - the blob used in this project is just an image
  ![Screenshot (73)](https://github.com/user-attachments/assets/687032d5-3d91-482f-b48e-fe5bf582b325)
- Select the Blob (file) you just uploaded. You should be on the properties tab.
- Copy the URL from the URL field and paste it into a new tab. You should be able to view it because you allowed it you can set it to private if you do not want it to be viewed in the public. url is https://bobosmomosstorage1.blob.core.windows.net/austin-container/1.jpg










