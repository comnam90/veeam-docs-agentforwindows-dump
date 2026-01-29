---
title: "Step 8. Select Restore Point"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/baremetal_point.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Step 8. Select Restore Point


At the Restore Point step of the wizard, select a restore point from which you want to recover data.

By default, Veeam Agent for Microsoft Windows uses the latest restore point. However, you can select any valid restore point to recover files and folders to a specific point in time.

Veeam Agent displays only restore points of volume-level backups. For example, if you have run 2 job sessions to create a backup of all computer volumes and then changed the backup scope to file-level backup, Veeam Agent will display only 2 restore points in the list.

![Step 8. Select Restore Point](images/ep_baremetal_point.webp "Select Restore Point")


