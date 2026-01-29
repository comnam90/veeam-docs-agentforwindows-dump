---
title: "Backup to Object Storage"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_to_object_storage.html"
last_updated: "10/1/2024"
product_version: "13.0.1.1009"
---

# Backup to Object Storage


If you want to store your data in a cloud-based or on-premises object storage, you can create backup jobs targeted at the object storage or another storage that uses object storage as a back end.

You can store Veeam Agent backups in the following object storage types:

* S3 compatible (including Wasabi Cloud Storage and IBM Cloud Object Storage)
* Amazon S3
* Google Cloud Storage
* Microsoft Azure Blob Storage
* Veeam Data Cloud Vault added as a Veeam backup repository or Veeam Cloud Connect repository. To learn more, see [Backup Destinations](#target).

Depending on your backup infrastructure, object storage can be available in different configurations. To learn more, see the following subsections:

* [Backup Destinations](#target)
* [Types of Connection to Object Storage in Veeam Backup & Replication](#connect)
* [Considerations and Limitations](#limitations)

Backup Destinations

You can back up Veeam Agent computer data to object storage in the following ways:

* Directly to object storage. In this case, Veeam Agent connects to the object storage and creates a backup repository in this storage.

Keep in mind that to connect to object storage, you need to specify an account with access permissions to read and write data.

To learn more, see [Object Storage Settings](backup_job_object_storage.md).

* To object storage added as a Veeam backup repository. In this case, an object storage repository is created in Veeam Backup & Replication. Veeam Agent connects to Veeam Backup & Replication and uses this Veeam backup repository.

To learn more, see [Veeam Backup Repository Settings](backup_job_vbr.md).

* To object storage added as a Veeam Cloud Connect repository. In this case, a Veeam Cloud Connect service provider creates an object storage repository in Veeam Backup & Replication and exposes it as a cloud repository to tenants. Veeam Agent connects to the service provider and uses the Veeam Cloud Connect repository.

To learn more, see [Veeam Cloud Connect Repository Settings](backup_job_sp_settings.md).

Connection Types

If you back up data to object storage added as a Veeam backup repository or Veeam Cloud Connect repository, you must configure a repository beforehand on the Veeam Backup & Replication side. Depending on the repository configuration, Veeam Backup & Replication provides one of the following connection types to the repository in the object storage:

* Connection through a gateway server. With this connection type, Veeam Agent connects to the repository using a proxy component — a gateway server that is assigned in the Veeam Backup & Replication console. The backup data is transferred from the Veeam Agent computer to the gateway server, then it is transferred from the gateway server to the repository.

* Direct connection. With this connection type, Veeam Agent connects directly to the repository. The backup data is transferred from the Veeam Agent computer to the repository without proxy components. The access to this repository is managed by Application Programming Interface (API) that is provided by an external cloud service provider.

Considerations and Limitations

Before you configure a backup job to store backups in object storage, consider the following:

* Veeam Agent does not support backup to object storage for which lifecycle rules are enabled. Enabling lifecycle rules may result in backup and restore failures.

* For backups located in object storage, synthetic full backup method is not supported.
* For backups located in object storage, compact full backup file option is not supported.

* You cannot back up data to the Microsoft Azure Blob Storage added in the direct connection mode under the general-purpose V1 storage account type.
* You cannot back up data to the Veeam Data Cloud Vault storage added in the direct connection mode.

* You can store backups only in those S3 compatible storage repositories that are accessible over the HTTPs protocol.
* [For object storage added as a Veeam backup repository or Veeam Cloud Connect repository] If you want to back up your data to the S3 compatible storage using a direct connection, you must additionally specify access permissions settings for the storage. To do so, enable the Agents share credentials to object storage repository or the Provided by IAM/STS object storage capabilities access control option. To learn more, see the [Managing Permissions for S3 Compatible Object Storage](https://helpcenter.veeam.com/docs/vbr/userguide/access_permissions.html?ver=13#managing-permissions-for-s3-compatible-object-storage) section in the Veeam Backup & Replication User Guide.
* [For object storage added as a Veeam backup repository or Veeam Cloud Connect repository] Data recovery options are not available if you access the object storage repository using credentials with the read-only access permissions.
* [For object storage added as a Veeam backup repository or Veeam Cloud Connect repository] If Veeam Backup & Replication uses [HTTP or HTTPS proxies](https://helpcenter.veeam.com/docs/vbr/userguide/hmc_configure_proxies.html?ver=13), backup to object storage is only available through a gateway server.
* [For object storage added as a Veeam backup repository] If you back up data to the S3 compatible object storage with multiple buckets, Veeam Agent will ignore the number of workloads set for one bucket and will store all backups, created under a specific account that has access to the repository, in a single child bucket. To learn more about multiple buckets, see the [Multiple Buckets for S3 Compatible Object Storage Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/object_storage_repository.html?ver=13#multiple-buckets-for-s3-compatible-object-storage-repositories) section in the Veeam Backup & Replication User Guide.

* If you have a backup job targeted at an object storage added as an extent of a scale-out backup repository in the direct connection mode and you put this extent to the Maintenance or Seal mode during the backup job session while there is no connection between Veeam Backup & Replication and the object storage, the current and subsequent backup job sessions will end successfully.

To learn about modes you can put extents of scale-out backup repositories to, see the [Service Actions with Scale-Out Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/backup_repository_sobr_service.html?ver=13) section in the Veeam Backup & Replication User Guide.


