---
title: "How Volume Extend Works"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/extend_hiw.html"
last_updated: "11/22/2023"
product_version: "13.0.1.1009"
---

# How Volume Extend Works


When you restore a volume to a target location of the larger size, Veeam Agent for Microsoft Windows performs the following operations:

1. When you select the Resize option to extend a volume, Veeam Agent for Microsoft Windows mounts the backup volume to a temporary NTFS folder on the system drive, for example: C:\Users\Username\AppData\Local\Temp.
2. Veeam Agent for Microsoft Windows mounts the created NTFS folder as a VHD disk next to other disks that are present on the computer.

Mounting VBK file content as a VHD disk makes it possible for Veeam Agent for Microsoft Windows to use Microsoft Windows system's disk management tools to measure current size of the backup volume and maximum and minimum size for the restored volume.

1. Veeam Agent for Microsoft Windows sends a query request to the mounted VHD disk to calculate its size, amount of stored data and free disk space by which the volume can be extended.

This step may take some time depending on the size of the backup volume and its data fragmentation ratio.

When the query is complete and you specify the desired size for the restored volume, Veeam Agent for Microsoft Windows unmounts the VHD disk.

1. When you start the restore process, Veeam Agent for Microsoft Windows creates on the target disk a volume of the same size as the backup volume and restores to that volume all data blocks from the backup volume.
2. When all data blocks are written to the target location, Veeam Agent for Microsoft Windows extends the size of the target volume to the specified size.

![How Volume Extend Works](images/endpoint_scheme_extend.webp "Volume Extend Process")


