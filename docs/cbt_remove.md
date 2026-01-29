---
title: "Removing Veeam CBT Driver"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/cbt_remove.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Removing Veeam CBT Driver


You can quickly remove the Veeam CBT driver, for example, if your Veeam Agent computer does not run applications with large database files any more, and you do not need to perform advanced change block tracking on this computer.

To remove the Veeam CBT driver:

1. Double-click the Veeam Agent for Microsoft Windows icon in the system tray, or right-click the Veeam Agent for Microsoft Windows icon in the system tray and select Control Panel.
2. From the main menu, select Settings.
3. Click Uninstall.
4. To complete the uninstallation process, Veeam Agent for Microsoft Windows needs to reboot the computer. To reboot the computer immediately, in the displayed window, click Yes. After computer reboot, Veeam Agent for Microsoft Windows will use the default CBT mechanism to get the list of changed data blocks.

|  |
| --- |
| ![Removing Veeam CBT Driver](images/icon_tip.webp) TIP |
| You can also uninstall the Veeam CBT driver in the Microsoft Windows control panel:   1. From the Start menu, select Control Panel > Programs and Features. 2. In the programs list, right-click Veeam CBT Driver and select Uninstall. 3. In the displayed window, click Yes. |

![Removing Veeam CBT Driver](images/cbt_remove.webp "Reboot Computer After CBT Driver Removal")


