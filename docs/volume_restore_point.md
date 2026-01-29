---
title: "Step 6. Select Restore Point"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/volume_restore_point.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Step 6. Select Restore Point


At the Restore Point step of the wizard, select a restore point from which you want to recover data.

By default, Veeam Agent for Microsoft Windows uses the latest restore point. However, you can select any valid restore point to recover volumes to a specific point in time.

Veeam Agent for Microsoft Windows displays restore points for volume-level backups only. For example, if you have run 3 job sessions to create a backup of all computer volumes and then changed the backup scope to file-level backup, Veeam Agent for Microsoft Windows will display only 3 restore points in the list.

![Step 6. Select Restore Point](images/ep_volume_restore_point.webp "Select Restore Point")


