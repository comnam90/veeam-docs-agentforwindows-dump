---
title: "Standalone and Managed Operation Modes"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/operation_modes.html"
last_updated: "10/23/2023"
product_version: "13.0.1.1009"
---

# Standalone and Managed Operation Modes


Veeam Agent can operate in two modes: standalone mode and managed mode. The current User Guide covers subjects related to Veeam Agent operating in the standalone mode only. Depending on the operation mode, Veeam Agent has different functionality and limitations.

Standalone Mode

In this mode, Veeam Agent operates as a standalone product. To use Veeam Agent operating in the standalone mode, you must manually install the product directly on the computer whose data you want to protect.

For Veeam Agent operating in the standalone mode, data protection, disaster recovery and administration tasks are performed by the user. You can also use Veeam Agent operating in the standalone mode with Veeam Backup & Replication. In this scenario, you can use backup repositories managed by Veeam Backup & Replication as a target location for Veeam Agent backups and use the Veeam Backup & Replication console to perform a number of tasks with Veeam Agent backup jobs and backups. To learn more, see [Integration with Veeam Backup & Replication](vbr_integration.md).

You can also use Veeam Backup & Replication as a gateway for creating backups targeted at the following types of repositories:

* Veeam Cloud Connect repository. To learn more, see [Backup to Veeam Cloud Connect](cloud_connect.md).
* Object storage repository.

With Veeam Agent operating in the standalone mode, you can also back up data directly to object storage. To learn more about both options, see [Backup to Object Storage](backup_to_object_storage.md).

Managed Mode

In this mode, Veeam Agent operates under control from one of the following Veeam products:

* Veeam Backup & Replication

You can automate management of Veeam Agents on multiple computers in your infrastructure in the Veeam Backup & Replication console. You can configure Veeam Agent backup policies and perform other data protection and administration tasks on remote computers.

To use Veeam Agent operating in the managed mode, you must deploy the product in one of the following ways:

* From Veeam Backup & Replication
* Manually using external tools

To learn more about managed Veeam Agent deployment, see the [Protected Computers Discovery and Veeam Agent Deployment](https://helpcenter.veeam.com/docs/vbr/userguide/agents_discovery_and_deployment.html?ver=13) section in the Veeam Backup & Replication User Guide.

For Veeam Agent managed by Veeam Backup & Replication, data protection, data restore and administration tasks are performed by a backup administrator in the Veeam Backup & Replication console. To learn about managing Veeam Agent in Veeam Backup & Replication, see the [Veeam Agent Backup](https://helpcenter.veeam.com/docs/vbr/userguide/protect_comp.html?ver=13) section in the Veeam Backup & Replication User Guide.

* Veeam Service Provider Console

You can use Veeam Service Provider Console to manage Veeam Agents on multiple computers in your infrastructure. When Veeam Agent is managed by Veeam Service Provider Console, you can configure backup job settings, start and stop backup, change global settings, update and uninstall Veeam Agent and collect Veeam Agent data for monitoring and billing.

To manage Veeam Agent from Veeam Service Provider Console, you must install Veeam Service Provider Console management agent and Veeam Agent on the computer whose data you want to protect. After that, in Veeam Service Provider Console, you must activate Veeam Agent on the protected computer to set it into the managed operation mode.

For Veeam Agent managed by Veeam Service Provider Console, data protection, data restore and administration tasks are performed by a backup administrator in Veeam Service Provider Console.

Backup administrator can enable a read-only access mode for Veeam Agent installed on the protected computer. When you work directly with Veeam Agent operating in the read-only access mode, you can perform a limited set of operations, including:

* Running the backup job manually.
* Viewing backup session statistics.
* Restoring individual files.

To learn about deploying and managing Veeam Agent with Veeam Service Provider Console, see [Veeam Service Provider Console User Guides](https://www.veeam.com/documentation-guides-datasheets.html?productId=49). Select the guide that suits your user role.

Related Topics

* [Integration with Veeam Backup & Replication](vbr_integration.md)
* [Managing Veeam Agent in Veeam Backup & Replication](agent_management.md)


