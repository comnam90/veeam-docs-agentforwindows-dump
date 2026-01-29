---
title: "Job Retry"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/job_retry.html"
last_updated: "11/22/2023"
product_version: "13.0.1.1009"
---

# Job Retry


You can instruct Veeam Agent for Microsoft Windows to retry the backup job several times if the initial job session fails. By default, Veeam Agent for Microsoft Windows automatically retries a failed job for 3 times within one job session. If necessary, however, you can define a custom number of retries in the job settings.

If a backup job fails and Veeam Agent retries the job session, Veeam Agent does not transfer all the data again. Instead, Veeam Agent continues data transfer that was started before the backup job fail. To do so, Veeam Agent compares hash values for data blocks on source and target. After the hash comparison, Veeam Agent also transfers only those data blocks that were not transferred before the job fail. If data blocks on source were changed before the retry, Veeam Agent transfers these data blocks as well.

If you edit certain job configuration options before the retry, Veeam Agent may require to transfer all the data to target again. These options include backup scope, data compression, storage optimization, data encryption. Keep in mind that if you back up data to the Veeam backup repository and change data encryption options on the Veeam Backup & Replication side, Veeam Agent transfers all the data to the repository again.

Veeam Agent does not fail the backup job session in case Veeam Agent computer is put into sleep or hibernate mode during the job session, and the backup job is targeted at one of the following locations:

* Local computer drive
* Network shared folder

After the computer is turned on and the connection is restored, Veeam Agent operates in the same way as in case of job retry. Veeam Agent does not transfer all the data again, but continues the job session from the point where it stopped.

Limitations for Job Retry

* Veeam Agent continues data transfer after the backup job fail only if you configured a job that creates volume-level backups. To learn more about volume-level backups, see [Volume-Level Backup](volume_backup.md).

* Veeam Agent does not perform retry for jobs started manually.
* Veeam Agent does not retry the backup job if the job session is started when the computer is powered on after missed daily backup.
* Veeam Agent retries a job only if the previous job session has failed. Veeam Agent does not perform a retry if a job session has finished with the Success or Warning status.
* For portable devices, Veeam Agent does not retry the backup job if a device is working on battery and the battery level is below 20%.


