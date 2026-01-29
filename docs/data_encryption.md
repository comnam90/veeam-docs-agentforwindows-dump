---
title: "Data Encryption"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/data_encryption.html"
last_updated: "3/15/2024"
product_version: "13.0.1.1009"
---

# Data Encryption


Data security is an important part of the backup strategy. You must protect your information from unauthorized access, especially if you back up sensitive data to remote locations. To keep your data safe, you can use data encryption.

Data encryption transforms data to an unreadable, scrambled format with the help of a cryptographic algorithm and a secret key. If encrypted data is intercepted, it cannot be unlocked and read by the eavesdropper. Only intended recipients who know the secret key can reverse encrypted information back to a readable format.

Encryption is performed on the trusted side depending on the backup target:

* Encryption is performed on the source side for all backup targets except the Veeam backup repository.
* Encryption is performed on the target side if you store backups in the Veeam backup repository.

Decryption is performed on the same side as encryption.

To create encrypted backups, you must enable the encryption option and specify a password that will be used for data encryption. To learn more, see [Storage Settings](backup_job_advanced_storage.md).

|  |
| --- |
| NOTE |
| You cannot specify encryption options for the backup job if you have chosen to save Veeam Agent backups in a Veeam backup repository. For such jobs, encryption options are managed per repository by a backup administrator working with Veeam Backup & Replication. To learn more, see the [Encrypting Standalone Application Backups in Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/encrypting_backups.html?ver=13) section in the Veeam Backup & Replication User Guide. |

In This Section

* [How Data Encryption Works](encryption_hiw.md)
* [How Data Decryption Works](decryption_hiw.md)

* [Continuing Encrypted Backup Chain](encrypted_backup_chain.md)

Related Tasks

* [Creating Backup Jobs](backup_job_create.md)
* [Restoring Data from Encrypted Backups](restore_encrypted.md)


