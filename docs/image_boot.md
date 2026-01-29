---
title: "Restoring from Veeam Recovery Media"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/image_boot.html"
last_updated: "11/26/2024"
product_version: "13.0.1.1009"
---

# Restoring from Veeam Recovery Media


If the OS on your computer fails to start, you can use the Veeam Recovery Media to recover your computer. The Veeam Recovery Media will help you boot the computer in the limited mode. After booting, you can use Veeam Agent for Microsoft Windows or standard Microsoft Windows tools to diagnose problems and fix errors. You can also use a backup created with Veeam Agent for Microsoft Windows to restore the whole system image of your computer or specific volumes on your computer.

Before you boot from the Veeam Recovery Media, [check prerequisites](baremetal_byb.md). Then launch the restore process depending on the operation mode set for the created Veeam Recovery Media:

* [Restoring from Veeam Recovery Media in the Manual Mode](image_boot_manual.md) — if the operation mode is set to Manual.
* [Restoring from Veeam Recovery Media in the Unattended Mode](image_boot_unattended.md) — if the operation mode is set to Prompt.

To learn more about the Veeam Recovery Media operation modes, see [Defining Veeam Recovery Media Restore Mode](image_mode.md).

Related Topics

* [Volume-Level Restore](restore_volume.md)
* [Veeam Recovery Media](recovery_media.md)


