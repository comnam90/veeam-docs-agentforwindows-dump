---
title: "How Synthetic Full Backup Works"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/synthetic_full_hiw.html"
last_updated: "2/2/2026"
product_version: "13.0.1.1009"
---

# How Synthetic Full Backup Works


To create a synthetic full backup, Veeam Agent performs the following steps:

1. On a day when synthetic full backup is scheduled, Veeam Agent triggers a new backup job session. During this session, Veeam Agent first creates an incremental backup and adds it to the backup chain. This incremental backup helps Veeam Agent ensure that the synthetic full backup includes the latest changes of the backed-up data.

![How Synthetic Full Backup Works](images/synthetic_fulls_hiw_1.webp "New Temporary Restore Point in Backup Chain")

1. At the end of the backup job session, Veeam Agent builds a new synthetic full backup using backup files that are already available in the backup chain, including the newly created incremental backup file.

![How Synthetic Full Backup Works](images/synthetic_fulls_hiw_2.webp "Creation of New Synthetic Backup ")

1. When the synthetic full backup is created, Veeam Agent deletes the incremental backup file created at the beginning of the job session. As a result, you have a backup chain that consists of a full backup file, set of incremental backup files and synthetic full backup file.

![How Synthetic Full Backup Works](images/synthetic_fulls_hiw_3.webp "Removal of Temporary Restore Point ")

1. Every next job session creates a new incremental restore point starting from the synthetic full backup until the day on which synthetic full backup is scheduled. On this day, Veeam Agent creates a new synthetic full backup.


