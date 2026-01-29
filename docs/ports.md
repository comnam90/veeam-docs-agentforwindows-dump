---
title: "Ports"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/ports.html"
last_updated: "12/23/2025"
product_version: "13.0.1.1009"
---

# Ports


|  |
| --- |
| NOTE |
| The following tables describe network ports that must be opened to ensure proper communication of Veeam Agent operating in the standalone mode with other infrastructure components.  To learn about ports required to enable proper work of Veeam Agent for Microsoft Windows managed by Veeam Backup & Replication, see the [Ports](https://helpcenter.veeam.com/docs/vbr/userguide/agents_used_ports.html?ver=13) section in the Veeam Backup & Replication User Guide. |

|  |
| --- |
| ![Ports](images/icon_important.webp) IMPORTANT |
| The list of ports required for computers booted from the Veeam Recovery Media is the same as the list of ports required for Veeam Agent computers. |

The following table describes network ports that Veeam Agent for Microsoft Windows requires to be open on the Veeam Agent computer to operate successfully:

| Protocol | Port | Notes |
| --- | --- | --- |
| TCP | 6183, | Ports used locally on the Veeam Agent computer for communication between Veeam Agent components and Veeam Agent for Microsoft Windows Service, and between  Veeam Agent components and backup targets. |

The following tables describe network ports that must be opened on the target to ensure proper communication of Veeam Agent for Microsoft Windows with backup infrastructure components:

* [Outgoing Connections](#outgoing)
* [Incoming Connections](#incoming)

Outgoing Connections

Communication Between Veeam Agent Components

The following table describes network ports that must be opened to enable proper communication between Veeam Agent for Microsoft Windows components.

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | Veeam Agent computer | TCP | 6183, 2500 to 3500, 49152 to 65535 | Ports used locally on the Veeam Agent computer for communication between Veeam Agent components and Veeam Agent for Microsoft Windows Service. |
| Veeam Update Notification Server (agents.butler.veeam.com) | TCP | 443 | Default port used to download information about available updates from the Veeam Update Notification Server over the Internet. |

Communication with Veeam Backup Repositories

The following table describes network ports that must be opened to ensure proper communication with backup repositories added to the Veeam Backup & Replication infrastructure.

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | Veeam backup server | TCP | 10005 | Default port used by Veeam Agent for Microsoft Windows for communication with the Veeam Backup server.  Port used by Veeam Agent for direct connection to the Veeam backup server using a recovery token during bare metal restore.  Data between the Veeam Agent computer and backup repositories is transferred directly, bypassing Veeam backup servers. |
| TCP | 443 | Port used by Veeam Agent to obtain authentication tokens from Veeam Backup Identity Service. |
| Veeam backup repository | TCP | 6162, 2500 to 3300 | Default range of ports used as data transmission channels. |
| Gateway server | TCP UDP | 137 to 139,  445 | If an SMB (CIFS) share is used as a backup repository and a Microsoft Windows server is selected as a gateway server for this CIFS share, these ports must be opened on the gateway Microsoft Windows server.  Ports 137 to 139 are used by backup infrastructure components to communicate using NetBIOS. |
| TCP | 49152 to 65535 | Dynamic RPC port range. For more information, see [Microsoft documentation](https://support.microsoft.com/kb/929851/en-us). |
| TCP | 6162, 2500 to 3300 | Default range of ports used as data transmission channels. |

Communication with Veeam Cloud Connect Repositories

The following table describes network ports that must be opened to ensure proper communication with Veeam Cloud Connect repositories.

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | Cloud gateway | TCP | 6180+ | Port on the cloud gateway used to transport Veeam Agent data to the Veeam Cloud Connect repository. |
| Certificate revocation lists | TCP | 80 or 443 (most popular) | Veeam Agent computer needs access to CRLs (Certificate Revocation Lists) of the CA (Certification Authority) who issued a certificate to the Veeam Cloud Connect service provider.  Generally, information about CRL locations can be found on the CA website. |

Communication with Object Storage

The following table describes network ports that must be opened to ensure proper communication with object storage if you back up data to object storage directly or to object storage added as a Veeam backup repository with the direct connection mode. For more information about object storage connection modes, see [Connection Types](backup_to_object_storage.md#connect).

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | Amazon S3 object storage | TCP | 443 | Used to communicate with the Amazon S3 object storage through the following endpoints:   * \*.amazonaws.com (for both Global and Government regions) * \*.amazonaws.com.cn (for China region)   All AWS service endpoints are specified in the [AWS documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region). |
| 80 | Used to verify the certificate status through the following endpoints:   * \*.amazontrust.com * \*.cloudfront.net   Consider that certificate verification endpoints (CRL URLs and OCSP servers) are subject to change. The actual list of addresses can be found in the certificate itself. |
| Microsoft Azure object storage | TCP | 443 | Used to communicate with the Microsoft Azure object storage through the following endpoints:   * <storage-account>.blob.core.windows.net (for Global region) * <storage-account>.blob.core.chinacloudapi.cn (for China region) * <storage-account>.blob.core.usgovcloudapi.net (for Government region)   Consider that the <storage-account> part of the address must be replaced with your actual storage account URL that can be found in the Azure management portal. |
| 80 | Used to verify the certificate status through the following endpoints:   * ocsp.digicert.com * oneocsp.microsoft.com   Consider that certificate verification endpoints (CRL URLs and OCSP servers) are subject to change. The actual list of addresses can be found in the certificate itself. For more details, see also [Microsoft documentation](https://learn.microsoft.com/en-us/azure/security/fundamentals/azure-CA-details?tabs=root-and-subordinate-cas-list#certificate-downloads-and-revocation-lists). |
| Google Cloud storage | TCP | 443 | Used to communicate with Google Cloud storage through the following endpoints:   * storage.googleapis.com   All cloud endpoints are specified in [this Google article](https://cloud.google.com/storage/docs/request-endpoints). |
| 80 | Used to verify the certificate status through the following endpoints:   * ocsp.pki.goog * pki.goog * crl.pki.goog   Consider that certificate verification endpoints (CRL URLs and OCSP servers) are subject to change. The actual list of addresses can be found in the certificate itself. |
| IBM Cloud object storage | TCP | Depends on device configuration | Used to communicate with IBM Cloud object storage. |
| S3 compatible object storage | TCP | Depends on device configuration | Used to communicate with S3 compatible object storage. |

Communication with Shared Folder Targets

The following table describes network ports that must be opened to ensure proper communication between Veeam Agent and shared folder targets outside the Veeam Backup & Replication infrastructure.

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | Shared folder SMB (CIFS) share | TCP | 139, 445 | Ports used as a transmission channel from the Veeam Agent computer to the target SMB (CIFS) share.  Ports 137-139 are used by backup infrastructure components to communicate using NetBIOS if you use NetBIOS in your infrastructure. |
| UDP | 137, 138 |

Communication with Mail Servers

The following table describes network ports that must be opened to ensure proper communication with mail servers.

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | SMTP server | TCP | 25 | Default port used by the SMTP server. |
| TCP | 587 | Port used by the SMTP server if SSL is enabled. |
| Gmail REST API (gmail.googleapis.com) | TCP | 443 | Port used for communication with Google Mail services. |
| Microsoft Graph REST API (graph.microsoft.com, login.microsoftonline.com) | TCP | 443 | Port used for communication with Microsoft Exchange Online organizations. |

Communication with Other Services

The following table describes network ports that must be opened to ensure proper communication with Microsoft Windows services.

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | DNS server | TCP | 135 | Port used for connection with Microsoft Endpoint Mapper to find available network services. |
| Active Directory Domain Controller | TCP | 389, 636, 49152 to 65535 | Ports used for communications over LDAP and LDAPS protocols. |

Incoming Connections

| From | To | Protocol | Port | Notes |
| --- | --- | --- | --- | --- |
| Veeam Agent computer | Veeam Agent computer | TCP | 6183, 2500 to 3500, 49152 to 65535 | Ports used locally on the Veeam Agent computer for communication between Veeam Agent components and Veeam Agent for Microsoft Windows Service. |
| Veeam backup server | TCP | 135, 445, 6160, 6162 2500 to 3300, 3260, 49152 to 65535 | Ports used by Veeam Backup & Replication for file-level restore and disk publishing. |


