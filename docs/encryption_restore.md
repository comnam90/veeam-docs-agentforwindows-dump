---
title: "Restore from Encrypted Backups"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/encryption_restore.html"
last_updated: "12/16/2024"
product_version: "13.0.1.1009"
---

# Restore from Encrypted Backups


When you restore data from an encrypted backup, Veeam Agent for Microsoft Windows performs data decryption in the following ways:

* If encryption keys required to unlock the backup file are available in the Veeam Agent for Microsoft Windows database, you do not need to specify the password. Veeam Agent for Microsoft Windows uses keys from the database to unlock the backup file. Data decryption is performed in the background, and data restore from the encrypted backup does not differ from that from an unencrypted one.

Automatic data decryption can be performed in one of the following situations:

* You encrypt and decrypt the backup file on the same Veeam Agent computer using the same Veeam Agent for Microsoft Windows database.
* You have included encryption keys into the Veeam Recovery Media and perform bare metal recovery after booting from this Veeam Recovery Media. To learn more, see [Specify Recovery Media Options](image_create_options.md).

* If encryption keys are not available in the Veeam Agent for Microsoft Windows database, you need to provide a password to unlock the encrypted file. The password must be the same as the password that was used to encrypt the backup file. If the password has changed once or several times, you need to specify the latest password. In Veeam Agent for Microsoft Windows, you can use the latest password to restore data from all restore points in the backup chain, including restore points that were encrypted with an old password and restore points that were created before you have enabled the encryption option for the job.

|  |
| --- |
| NOTE |
| Consider the following:   * If you store backups in the Veeam backup repository, encryption keys are not available in the Veeam Agent for Microsoft Windows database but Veeam Agent does not require a password. Such backups are encrypted and decrypted on the Veeam Backup & Replication side, and Veeam Agent considers such backups unencrypted. To learn more, see [Data Encryption](data_encryption.md). * You cannot restore data from a backup encrypted in Veeam Backup & Replication using KMS keys. |

Related Topic

[Data Encryption](data_encryption.md)

Related Task

[Restoring Data from Encrypted Backups](restore_encrypted.md)


