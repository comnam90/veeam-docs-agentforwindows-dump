---
title: "Drivers in Veeam Recovery Media"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/recovery_media_drivers.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Drivers in Veeam Recovery Media


The Veeam Recovery Media created with Veeam Agent for Microsoft Windows contains the following data:

* Set of files required to start your computer OS from the recovery media.
* Diagnostic tools from Microsoft and Veeam.
* Drivers required to run hardware and devices on your computer in a regular way. When you boot your computer from the Veeam Recovery Media, drivers included into the Veeam Recovery Media are automatically loaded on the recovered OS.
* Network connection settings from your computer. When you boot your computer from the Veeam Recovery Media, network settings included into the Veeam Recovery Media are automatically applied and can be used to connect to the remote backup storage.
* If you have enabled data encryption options for the backup job, you can also include a decryption key into the Veeam Recovery Media. To learn more, see [Creating Veeam Recovery Media](image_create.md).

|  |
| --- |
| ![Drivers in Veeam Recovery Media](images/icon_note.webp) NOTE |
| The Veeam Recovery Media contains all locales (languages) that are included in the OS of the Veeam Agent Computer. |

You can include the following drivers in the Veeam Recovery Media:

* Drivers that are currently installed on your computer. Veeam Agent for Microsoft Windows detects hard disk controller drivers, network adapter drivers and USB controller drivers and includes them into the Veeam Recovery Media.

* Additional storage and network drivers. If you use non-standard drivers, you can include them in the created Veeam Recovery Media manually. For example, you can include drivers for a discrete network card, third-party USB 3.0 controllers and non-standard hard disk controllers.

|  |
| --- |
| ![Drivers in Veeam Recovery Media](images/icon_tip.webp) TIP |
| If you do not include some drivers in the Veeam Recovery Media, you can load them from the computer drive when you perform bare metal recovery. To learn more, see [Restoring from Veeam Recovery Media](image_boot.md). |


