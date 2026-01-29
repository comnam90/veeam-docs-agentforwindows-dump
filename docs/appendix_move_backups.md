---
title: "Appendix B. Moving Veeam Agent Backups"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/appendix_move_backups.html"
last_updated: "11/11/2025"
product_version: "13.0.1.1009"
---

# Appendix B. Moving Veeam Agent Backups


A Veeam Agent backup job starts a new backup chain when you change a target location in the backup job settings. If you do not want the backup job to start a new backup chain, you can map a backup job to the previously made backups and continue the existing backup chain. For more information about backup chains, see [Backup Chain](backup_chain.md).

This appendix describes the following cases of moving Veeam Agent backups:

* [Move a Veeam Agent backup to the Veeam backup repository](appendix_move_backups_to_vbr.md).

In this section, scenarios describe how to move a locally stored backup to a Veeam backup repository and how to move a backup from one Veeam backup repository to another and continue the existing backup chain.

* [Move a Veeam Agent backup to the Veeam Cloud Connect repository](appendix_move_backups_to_vcc.md).

In this section, scenarios describe how to move a locally stored backup to a backup repository used as a cloud repository and continue the existing backup chain.

|  |
| --- |
| TIP |
| This appendix describes how to move backups created by Veeam Agent operating in the standalone mode. To learn how to move backups created by Veeam Agent operating in the managed mode, see the following topics:   * If Veeam Agent is managed by Veeam Backup & Replication, see the [Moving Backup](https://helpcenter.veeam.com/docs/vbr/userguide/agent_backup_move.html?ver=13) section in the Veeam Agent Management Guide. * If Veeam Agent is managed by Veeam Service Provider Console, see the [Moving Veeam Agent Backups](https://helpcenter.veeam.com/docs/vac/provider_admin/appendix_move_backups.html?ver=9.1) section in the Guide for Service Providers.   For more information about Veeam Agent operation modes, see [Standalone and Managed Operation Modes](operation_modes.md). |


