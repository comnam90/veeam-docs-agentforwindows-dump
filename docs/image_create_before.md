---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/image_create_before.html"
last_updated: "11/10/2025"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you create a Veeam Recovery Media, check the following prerequisites:

Removable Storage Device Scenario (USB, SD Card and Other)

* The removable storage device must be inserted into a corresponding slot on the computer or connected to the computer.
* The removable storage device must have enough capacity to store the created recovery image. On average, the size of the created recovery image without manually loaded drivers ranges from 600 to 900 MB.
* During the recovery image creation, Veeam Agent for Microsoft Windows formats the removable storage device. If you have important information on the device, create a copy of this data in some other location.
* If you want to include specific storage and network drivers into the recovery image, place them to a local folder on your computer or in a network shared folder to which you have access and read permissions. During the recovery image creation process, you will be able to define a path to this folder, and Veeam Agent for Microsoft Windows will include the drivers into the recovery image.
* [For Microsoft Windows Server versions, from 2012 R2 to 2022] If you want your computer to detect a Wi-Fi network and connect to it after you boot from the recovery image, enable the Wireless LAN Service feature on your computer. In this case, Veeam Agent for Microsoft Windows will add wireless networking support files to the Veeam Recovery Media. To learn more about the Wireless LAN Service, see [Microsoft documentation](https://technet.microsoft.com/en-us/library/hh994698.aspx).

Local Target and Shared Folder Scenario (ISO)

* If you want to include specific storage and network drivers into the recovery image, place them to a local folder on your computer or in a network shared folder on which you have read permissions. During the recovery image creation, you will be able to define a path to this folder, and Veeam Agent for Microsoft Windows will include the drivers into the recovery image.
* [For shared folders] If you plan to save the created ISO file in a network shared folder, make sure that you have access to this folder and write permissions on it.

* [For Microsoft Windows Server versions, from 2012 R2 to 2022] If you want your computer to detect a Wi-Fi network and connect to it after you boot from the recovery image, enable the Wireless LAN Service feature on your computer. In this case, Veeam Agent for Microsoft Windows will add wireless networking support files to the Veeam Recovery Media. To learn more about the Wireless LAN Service, see [Microsoft documentation](https://technet.microsoft.com/en-us/library/hh994698.aspx).


