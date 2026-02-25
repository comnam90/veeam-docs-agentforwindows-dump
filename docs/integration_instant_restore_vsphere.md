---
title: "Restoring Veeam Agent Backup to vSphere VM"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_instant_restore_vsphere.html"
last_updated: "2/24/2026"
product_version: "13.0.1.1009"
---

# Restoring Veeam Agent Backup to vSphere VM


In the Veeam Backup & Replication console, you can use Instant Recovery to restore a Veeam Agent computer as a VMware vSphere VM in your virtualization environment.

A restored VMware vSphere VM will have the same settings as the backed-up Veeam Agent computer. During the restore process, Veeam Backup & Replication retrieves the settings of the Veeam Agent computer from the backup and applies them to the target VM. These settings include:

* Amount of RAM.
* Number of CPU cores.
* Number of network adapters.
* Network adapter settings.
* BIOS UUID.

If you do not want to preserve the backed-up machine UUID for a VMware vSphere VM, you can create a new UUID during the Instant Recovery configuration process.

* Number of disks and volumes.
* Size of volumes.

Considerations and Limitations

If you restore a Veeam Agent computer to a VMware vSphere VM, consider the following:

* You can use entire machine or volume-level backups of Microsoft Windows computers. Volume-level backups must include the computer system drive.
* You can use backups of Microsoft Windows computers stored in a Veeam backup repository only. You cannot perform this operation with Veeam Agent backups stored in a Veeam Cloud Connect repository.
* Make sure that the target host has enough resources for a new VM. Otherwise, your VM will reduce the target host performance.

* If you restore a workload to the production network, make sure that the original workload is powered off.

Restore to vSphere VM

The procedure of Instant Recovery for a Veeam Agent computer practically does not differ from the same procedure for a VM. The main difference from Instant Recovery is that you do not need to select the recovery mode, because Veeam Agent computers are always restored to a new location. To learn more, see the [Performing Instant Recovery of Workloads to VMware vSphere](https://helpcenter.veeam.com/docs/vbr/userguide/performing_instant_recovery_vm.html?ver=13) section in the Veeam Backup & Replication User Guide.

[![Restore Veeam Agent Backup to vSphere VM](images/agent_restore_instant.webp)](images/agent_restore_instant.webp "Restore Veeam Agent Backup to vSphere VM")


