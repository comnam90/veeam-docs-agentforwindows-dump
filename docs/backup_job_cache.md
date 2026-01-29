---
title: "Step 9. Specify Backup Cache Settings"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_job_cache.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Step 9. Specify Backup Cache Settings


The Backup Cache step of the wizard is available if you have chosen to save backup files in a remote storage: in object storage, in a network shared folder, in a Veeam backup repository or in a Veeam Cloud Connect repository.

Specify backup cache settings:

1. Select the Enable backup cache check box.
2. In the Location field, specify a path to the folder on your computer in which backup files must be stored.
3. In the Maximum size field, specify the size for the backup cache.

When defining the size of the backup cache, assume the following:

* Each full backup file may consume about 50% of the backed-up data size.
* Each incremental backup file may consume about 10% of the backed-up data size.

|  |
| --- |
| ![Step 9. Specify Backup Cache Settings](images/icon_tip.webp) TIP |
| For the backup cache, you can use a dedicated removable storage device, for example, a USB key or an SD card. In this case, the backup cache will not consume disk space on the local drive of the Veeam Agent computer. |

![Step 9. Specify Backup Cache Settings](images/ep_backup_job_cache.webp "Specify Backup Cache Settings")


