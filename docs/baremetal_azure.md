---
title: "Microsoft Azure Blob Storage Settings"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/baremetal_azure.html"
last_updated: "9/13/2023"
product_version: "13.0.1.1009"
---

# Microsoft Azure Blob Storage Settings


If you have selected to restore data from a backup file located in the Microsoft Azure Blob storage, specify the following settings:

1. [Specify account settings](#storage).
2. [Specify container settings](#bucket).

Specifying Account Settings

The Account step of the wizard is available if you have chosen to restore data from a backup file located in object storage.

To connect to the Microsoft Azure Blob storage, specify the following:

1. In the Account field, enter the storage account name.
2. In the Shared key field, enter the storage account shared key.

1. From the Region drop-down list, select the Microsoft Azure region. By default, Veeam Agent uses the Azure Global (Standard) region.

![Microsoft Azure Blob Storage Settings](images/ep_baremetal_azure_account.webp "Specify Microsoft Azure Account Settings")

Specifying Container Settings

The Container step of the wizard is available if you have chosen to restore data from a backup file located in the Microsoft Azure Blob storage and specified account settings to connect to the storage.

Specify settings for the container in the storage:

1. From the Container drop-down list, select a container in the storage.
2. In the Folder field, specify a folder in the container:

1. Select the Browse option.
2. In the Select Folder window, do the following:

1. Double-click the container name or click the arrow to the left of the container name to view the list of available folders.
2. Select the necessary folder and click OK.

![Microsoft Azure Blob Storage Settings](images/ep_baremetal_azure_container.webp "Specify Microsoft Azure Container Settings")


