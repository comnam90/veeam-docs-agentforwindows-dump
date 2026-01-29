---
title: "Managing Rotated Drives"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/managing_devices.html"
last_updated: "7/9/2024"
product_version: "13.0.1.1009"
---

# Managing Rotated Drives


You can use a rotated drives scheme for storing backups. To do this, you can create backups on several external drives (for example, USB or FireWire) and swap these drives when needed.

The drive on which you plan to store a backup must be registered in Veeam Agent for Microsoft Windows. If the drive is not registered, Veeam Agent for Microsoft Windows will not be able to detect the drive and store a backup on it.

|  |
| --- |
| TIP |
| When you target a backup job at an external drive for the first time, this drive is registered automatically. |

Consider the following limitations:

* You can register and unregister drives if you have selected to store backups on an external drive connected to the computer. If you have selected to store backups on a local computer drive, in a network shared folder or in a backup repository, registering options will be disabled.
* You cannot unregister all drives at once. At least one drive will remain registered in Veeam Agent for Microsoft Windows.

To register and unregister a drive in Veeam Agent for Microsoft Windows:

1. Double-click the Veeam Agent for Microsoft Windows icon in the system tray, or right-click the Veeam Agent for Microsoft Windows icon in the system tray and select Control Panel.
2. From the main menu, select Settings.
3. Click the Manage registered storage devices link.
4. In the list of devices, click Register/Unregister next to the necessary backup storage device.

![Managing Rotated Drives](images/register_device.webp "Register Storage Device")


