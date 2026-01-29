---
title: "Short-Term Retention Policy"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/retention.html"
last_updated: "10/29/2025"
product_version: "13.0.1.1009"
---

# Short-Term Retention Policy


Restore points in the backup chain are not kept forever. They are removed according to the retention policy. The short-term retention policy helps maintain the life cycle of restore points and make sure that backup files do not consume the whole disk space.

Veeam Agent retains restore points for a certain number of days. To learn more, see [General Short-term Retention Policy](retention_days.md).

You can also specify the retention policy for outdated backups — backups for which Veeam Agent does not create new restore points within a specified time period. To learn more, see [Retention Policy for Outdated Backups](retention_deleted_items.md).


