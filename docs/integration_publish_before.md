---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_publish_before.html"
last_updated: "2/11/2026"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you publish disks, check the following requirements and limitations:

* The necessary ports must be opened on the target server. For more information, see [Ports](ports.md).
* The target server must support the file system of the disk that you plan to publish.
* If data deduplication is enabled for some disks in a backup, data deduplication must be enabled on the target server.
* The target Microsoft Windows server must support the same ReFS version or later than the version used on the Veeam Agent computer from which you plan to publish disks. For more information on which OSes support which ReFS, see the [ReFS versions and compatibility matrix](https://gist.github.com/0xbadfca11/da0598e47dd643d933dc#mountability).

For the full list of limitations, see the [Considerations and Limitations](https://helpcenter.veeam.com/docs/vbr/userguide/data_integration_api.html?ver=13#considerations-and-limitations) section in the Veeam Backup & Replication User Guide.


