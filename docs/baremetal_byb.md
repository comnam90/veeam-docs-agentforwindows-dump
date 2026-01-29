---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/baremetal_byb.html"
last_updated: "1/22/2026"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you boot from the recovery image and recover your data, check the following prerequisites:

* You must have a successfully created recovery image stored on a removable storage device, or as an ISO file burned to a CD, DVD, or Blu-ray disk.
* To recover data on your computer, you must have both the Veeam Recovery Media and data backup. For data recovery, you can use a volume-level backup created with Veeam Agent for Microsoft Windows or system image created with Microsoft Windows. Make sure that the backup or system image is available on the computer drive (local or external), in object storage, in a network shared folder, in the backup repository managed by a Veeam backup server or in the cloud repository.

|  |
| --- |
| IMPORTANT |
| Bare metal restore from a backup created by a backup copy job is only possible if the backup resides in the Veeam backup repository or Veeam Cloud Connect repository. For example, bare metal restore from such a backup exported to a local drive or SMB share is not supported.  For more information about backup copy jobs, see [Performing Backup Copy for Veeam Agent Backups](integration_backup_copy.md). |

* The media type on which you have created the recovery image must be set as a primary boot source on your computer.

Consider the following:

* When you create a Veeam Recovery Media, Veeam Agent for Microsoft Windows stores settings for languages added to the list of input languages on your computer. If necessary, you can switch between languages using a hotkey combination when working with the Veeam Recovery Media wizard. The default key combination is typically [Shift] + [Alt].
* NIC Teaming is not supported by Veeam Recovery Media due to limitations of the Windows Recovery Environment. To avoid network connection issues in Veeam Recovery Media, we recommend disabling NIC Teaming in the network switch configuration.
* Wireless networks that use the WPA3 security protocol are not supported by Veeam Recovery Media due to limitations of the Windows Recovery Environment.
* You can open the Command Prompt at any moment. To do this, press [Shift] + [F10] on the keyboard.
* If you perform restore on a tablet, you can use a virtual keyboard to enter necessary restore settings in the Veeam Recovery Media wizard.


