---
title: "Removing CBT Driver with Veeam Recovery Media"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/cbt_remove_media.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Removing CBT Driver with Veeam Recovery Media


You can use the Veeam Recovery Media to remove the Veeam CBT driver from your Veeam Agent computer. This operation may be required, for example, if the OS on your computer fails to start after you have installed the Veeam CBT driver in Veeam Agent for Microsoft Windows.

To remove the Veeam CBT driver:

1. [Boot from the Veeam Recovery Media](baremetal_boot.md).
2. On the Veeam Recovery Media screen, click Tools > Command Prompt or press [Shift] + [F10].
3. Use a command with the following syntax:

|  |
| --- |
| X:\VeeamRecovery\Veeam.Endpoint.Recovery.exe -RemoveVeeamCBTDriver |

1. Reboot the Veeam Agent computer.

|  |
| --- |
| ![Removing CBT Driver with Veeam Recovery Media](images/icon_note.webp) NOTE |
| Veeam Agent for Microsoft Windows will remove the Veeam CBT Driver from the Veeam Agent computer. However, a record about the driver will remain in the Microsoft Windows control panel. To remove the record, from the Start menu, select Control Panel > Programs and Features. Then right-click Veeam CBT Driver in the programs list and select Uninstall. |


