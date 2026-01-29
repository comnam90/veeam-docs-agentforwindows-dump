---
title: "Backup Cache"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_cache.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Backup Cache


A remote storage specified as a target location for backup files may be unavailable at the time when the backup job must start. In this case, Veeam Agent cannot create a regular restore point upon the defined schedule. As a result, the backup chain on the remote storage will not contain a sequence of restore points that precisely complies with the backup schedule.

To overcome this limitation, Veeam Agent offers the concept of the backup cache. The backup cache is a temporary local storage in which Veeam Agent creates backup files in case the backed-up data cannot be transferred to a remote location. When the target location becomes available, Veeam Agent uploads backup files from the backup cache to the remote storage, adding regular restore points to the backup chain.

The backup cache lets you perform scheduled backup in due time ensuring that the resulting backup chain will contain "snapshots" of your data at desired points in time. This may be helpful, for example, for laptop users who go on business trips with no or limited access to the corporate network in which the backup location resides.

Technically, the backup cache is a local folder on the computer on which Veeam Agent is installed. A user can define a folder for the backup cache and the size of the backup cache in the backup job settings.

The backup cache is available if the following types of storage are chosen as a target location:

* Network shared folder
* Object storage
* Backup repository managed by a Veeam backup server
* Cloud repository managed by a Veeam Cloud Connect service provider

In This Section

* [How Backup Cache Works](backup_cache_hiw.md)
* [Limitations for Backup Cache](backup_cache_limitations.md)

Related Tasks

* [Creating Backup Jobs](backup_job_create.md)
* [Managing Backup Cache](backup_cache_manage.md)


