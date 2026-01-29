---
title: "Backup to Deduplicating Storage Appliances"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_to_dedup_storage_app.html"
last_updated: "11/21/2023"
product_version: "13.0.1.1009"
---

# Backup to Deduplicating Storage Appliances


You can store backups in the deduplicating storage appliances added as backup repositories. To learn the full lists of supported appliances and their requirements and limitations, see the [Deduplicating Storage Appliances](https://helpcenter.veeam.com/docs/vbr/userguide/deduplicating_storage_appliances.html?ver=13) section in the Veeam Backup & Replication User Guide.

If you want to use immutability with the deduplicating storage appliances, consider the limitations listed in the following subsections:

* [HPE StoreOnce Immutability and Veeam Agents](#so)
* [Dell Data Domain Immutability and Veeam Agents](#dd)

HPE StoreOnce Immutability and Veeam Agents

If you want to use immutability with HPE StoreOnce Catalyst repositories, make sure that the value for the Maximum ISV Controlled Data Retention setting in HPE StoreOnce exceeds or is equal to the value of each of the following settings configured in Veeam Backup & Replication:

* The immutability period specified in the backup repository settings.
* The long-term retention period configured in backup job settings.

If the value of at least one of these periods exceeds the maximum value set for immutability in HPE StoreOnce Catalyst Store, consider the following:

* If the immutability period specified in the backup repository settings exceeds the maximum value set for immutability in HPE StoreOnce Catalyst Store, Veeam Backup & Replication applies immutability to the created backups according to the maximum value set for immutability in HPE StoreOnce Catalyst Store.
* If the long-term retention period configured in backup job settings exceeds the maximum value set for immutability in HPE StoreOnce Catalyst Store, the immutability period for backups with GFS flags is set according to the maximum value set for immutability in HPE StoreOnce Catalyst Store. For example, if the backup is stored for 1 year, but the maximum value for immutability in HPE StoreOnce Catalyst Store is set to 6 months, the backups will be immutable for 6 months.

To learn more about immutability for the HPE StoreOnce Catalyst repositories, see the [HPE StoreOnce and Immutability](https://helpcenter.veeam.com/docs/vbr/userguide/deduplicating_appliance_storeonce.html?zoom_highlight=%22hpe+storeonce+and+immutability%22&ver=13#hpe-storeonce-and-immutability) section in the Veeam Backup & Replication User Guide.

Dell Data Domain Immutability and Veeam Agents

If you want to use immutability with the Dell Data Domain backup repository, make sure that the values of the following settings configured in Veeam Backup & Replication lie in the range between the minimum and maximum retention periods configured in Dell Data Domain:

* The immutability period specified in the backup repository settings.
* The long-term retention period configured in backup job settings.

The minimum and maximum values are included into the range.

If the value of at least one of these periods lies outside the established range, consider the following:

* If the immutability period specified in the backup repository settings lies outside the range between the minimum and maximum retention periods configured in Dell Data Domain, the immutability for backups is set equal to the nearest range value.
* If the long-term retention period configured in backup job settings lies outside the range between the minimum and maximum retention periods configured in Dell Data Domain, the immutability period for backups with GFS flags is set equal to the nearest range value. For example, if the backup is stored for 1 year, but the range for immutability in Dell Data Domain is set to from 2 to 6 months, the backups will be immutable for 6 months.

To learn more about immutability for the Dell Data Domain backup repositories, see the [Retention Lock](https://helpcenter.veeam.com/docs/vbr/userguide/dell_dd_supported_features.html?ver=13#retention-lock) section in the Veeam Backup & Replication User Guide.


