---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_volume_restore_before.html"
last_updated: "9/1/2025"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you begin the volume-level restore process, check the following prerequisites:

* The backup from which you plan to restore data must be successfully created at least once.
* The computer to which you want to restore a volume must be added to the Veeam Backup & Replication inventory and run Veeam Agent for Microsoft Windows operating in the standalone mode.

Volume-level restore has the following limitations:

* You cannot restore a system volume to a system volume of the original Veeam Agent computer or another computer with the running OS. To perform such restore, you need to boot the OS from the recovery image. To learn more, see [Restoring Data with Veeam Recovery Media](image_boot.md). You can also restore a system volume to a non-system volume that has enough free space.
* You cannot restore a volume to a volume on which the Microsoft Windows swap file is hosted.


