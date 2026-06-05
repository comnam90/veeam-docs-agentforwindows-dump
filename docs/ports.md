---
title: "Ports"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/ports.html"
last_updated: "6/4/2026"
product_version: "13.0.3.1220"
---

# Ports


The following tables describe network ports that must be opened to ensure proper communication of Veeam Agent operating in the standalone mode with other infrastructure components.

To learn about ports required to enable proper work of Veeam Agent for Microsoft Windows managed by Veeam Backup & Replication, see the [Ports](https://helpcenter.veeam.com/docs/vbr/userguide/agents_used_ports.html?ver=13) section in the Veeam Backup & Replication User Guide.

|  |
| --- |
| ![Ports](images/icon_important.webp) IMPORTANT |
| The list of ports required for computers booted from the Veeam Recovery Media is the same as the list of ports required for Veeam Agent computers. |

Communication with Veeam Backup Server

The following table describes network ports that must be opened to ensure proper communication between Veeam Agent computers and the Veeam backup server.

Communication with Veeam Backup Server

| From | To | Protocol | Port | Notes |
| Veeam Agent computer | Veeam backup server | TCP | 10005 | Port 10005 is the default port used by Veeam Agent for Microsoft Windows for communication with the Veeam backup server. Port 10005 is also used by Veeam Agent for direct connection to the Veeam backup server using a recovery token during bare metal restore.  Data between the Veeam Agent computer and backup repositories is transferred directly, bypassing Veeam backup servers. |
| TCP | 443 | Port used by Veeam Agent to obtain authentication tokens from the Veeam Backup Identity Service. |
| Veeam backup server | Veeam Agent computer | TCP | 135, 445, 6160,  6162, 2500 to 3300, 3260 | Ports used by Veeam Backup & Replication for file-level restore and disk publishing. |

Communication with Veeam Backup Repositories

The following table describes network ports that must be opened to ensure proper communication with backup repositories added to the Veeam Backup & Replication infrastructure.

Communication with Veeam Backup Repositories

| From | To | Protocol | Port | Notes |
| Veeam Agent computer | Veeam backup repository | TCP | 6162, 2500 to 3300 | Default port used by Veeam Data Mover Service.  Note: The port range 2500 to 3300 is optional. Only if port 6162 is unavailable, Veeam Plug-In uses the port range 2500 to 3300 for failover. |
| Gateway server | TCP UDP | 137 to 139,  445 | If an SMB (CIFS) share is used as a backup repository and a Microsoft Windows server is selected as a gateway server for this CIFS share, these ports must be opened on the gateway Microsoft Windows server.  Ports 137 to 139 are used by backup infrastructure components to communicate using NetBIOS. |
| TCP | 6162, 2500 to 3300 | Default port used by Veeam Data Mover Service.  Note: The port range 2500 to 3300 is optional. Only if port 6162 is unavailable, Veeam Plug-In uses the port range 2500 to 3300 for failover. |

Communication with Veeam Cloud Connect Repositories

The following table describes network ports that must be opened to ensure proper communication with Veeam Cloud Connect repositories.

Communication with Veeam Cloud Connect Repositories

| From | To | Protocol | Port | Notes |
| Veeam Agent computer | Cloud gateway | TCP | 6180+ | Port on the cloud gateway used to transport Veeam Agent data to the Veeam Cloud Connect repository. |
| Certificate revocation lists | TCP | 80 or 443 (most popular) | Veeam Agent computer needs access to CRLs (Certificate Revocation Lists) of the CA (Certification Authority) who issued a certificate to the Veeam Cloud Connect service provider.  Generally, information about CRL locations can be found on the CA website. |

Communication with Shared Folder Targets

The following table describes network ports that must be opened to ensure proper communication between Veeam Agent and shared folder targets outside the Veeam Backup & Replication infrastructure.

Communication with Shared Folder Targets

| From | To | Protocol | Port | Notes |
| Veeam Agent computer | Shared folder SMB (CIFS) share | TCP | 139, 445 | Ports used as a transmission channel from the Veeam Agent computer to the target SMB (CIFS) share.  Ports 137-139 are used by backup infrastructure components to communicate using NetBIOS if you use NetBIOS in your infrastructure. |
| UDP | 137,  138 |

Communication with Mail Servers

The following table describes network ports that must be opened to ensure proper communication with mail servers.

Communication with Mail Servers

| From | To | Protocol | Port | Notes |
| Veeam Agent computer | SMTP server | TCP | 25 | Default port used by the SMTP server. |
| TCP | 587 | Port used by the SMTP server if SSL is enabled. |
| Gmail REST API (gmail.googleapis.com) | TCP | 443 | Port used for communication with Google Mail services. |
| Microsoft Graph REST API (graph.microsoft.com, login.microsoftonline.com) | TCP | 443 | Port used for communication with Microsoft Exchange Online organizations. |

Communication with Other Services

The following table describes network ports that must be opened to ensure proper communication with other services, such as Microsoft Windows services.

Communication with Other Services

| From | To | Protocol | Port | Notes |
| Veeam Agent computer | Active Directory Domain Controller | UDP | 135 | Port 135 is used for connection with Microsoft Endpoint Mapper to find available network services. |
| Veeam Update Notification Server (agents.butler.veeam.com) | TCP | 443 | Default port used to download information about available updates from the Veeam Update Notification Server over the Internet. |

Communication Between Veeam Agent Components

The following table describes network ports that are required for communication between Veeam Agent for Microsoft Windows components.

|  |
| --- |
| NOTE |
| For Veeam Agent to operate successfully, make sure that these ports are available locally and not in use by other processes or applications. |

Communication Between Veeam Agent Components

| Protocol | Port | Notes |
| TCP | 6183, 2500 to 3500 | Ports used locally on the Veeam Agent computer for communication between Veeam Agent components and Veeam Agent for Microsoft Windows Service. |


