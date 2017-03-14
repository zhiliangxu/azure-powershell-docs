---
Module Name: ServiceFabric
Module Guid: ServiceFabric_d2c42633-5254-4a82-a31
Download Help Link: http://go.microsoft.com/fwlink/?LinkID=521412
Help Version: 2.0.14.0
Locale: en-US
ms.assetid: 8FE06792-E775-4575-8C55-12A66ED66383
uid: ServiceFabric
updated_at: 01/04/2017 02:01 AM
ms.date: 01/04/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/ServiceFabric.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/ServiceFabric.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/bd7e7939d172a05060cf108dbdf6b48bdb486cf0
ms.topic: conceptual
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# ServiceFabric Module
## Description
This topic displays help topics for the Azure Service Fabric Cmdlets.

Service Fabric is a distributed systems platform that makes it easy to package, deploy, and manage scalable and reliable microservices and addresses the significant challenges in developing and managing cloud applications.
By using Service Fabric, developers and administrators can avoid solving complex infrastructure problems and focus instead on implementing mission-critical, demanding workloads knowing that they are scalable, reliable, and manageable.
Service Fabric represents the next-generation middleware platform for building and managing these enterprise-class, Tier-1 cloud-scale applications.

With Azure Service Fabric, you can do the following:

* Simplify microservice-based application development and lifecycle management
* Deliver low-latency performance and efficiency at massive scale
* Proven platform used by Azure and other Microsoft services
* Run in Azure, on-premises, or in other clouds

The Service Fabric PowerShell module is installed with the [Service Fabric SDK, runtime, and tools](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-get-started).


## About Windows PowerShell

Windows PowerShell is a task-based command-line shell and scripting language designed for system administration.
Unlike most shells, which accept and return text, Windows PowerShell is built on top of the .NET Framework, and accepts and returns .NET Framework objects.

Windows PowerShell introduces the concept of a cmdlet (pronounced "command-let"), a simple, single-function command-line tool built into the shell.
Cmdlets have the following naming convention: a verb and noun separated by a dash (-), such as **Get-Help**, **Get-Process**, and **Start-Service**.
Windows PowerShell includes more than one hundred basic core cmdlets.

For more information about, or for the syntax of, any of the cmdlets, use the `Get-Help <cmdlet name>` command, where `<cmdlet name>` is the name of the cmdlet that you want to research.
For more detailed information, you can run any of the following commands:

* `Get-Help <cmdlet name> -Detailed`
* `Get-Help <cmdlet name> -Examples`
* `Get-Help <cmdlet name> -Full`

For more information about Windows PowerShell, see the [Getting Started with Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell).


## ServiceFabric Cmdlets
### [Add-ServiceFabricNode](./Add-ServiceFabricNode.md)
Adds a Service Fabric node to a cluster.


### [Approve-ServiceFabricRepairTask](./Approve-ServiceFabricRepairTask.md)
Forces approval of a repair task.


### [Complete-ServiceFabricRepairTask](./Complete-ServiceFabricRepairTask.md)
Reports that a manual repair task is finished.


### [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)
Creates a connection to a Service Fabric cluster.


### [Copy-ServiceFabricApplicationPackage](./Copy-ServiceFabricApplicationPackage.md)
Copies a Service Fabric application package to the image store.


### [Copy-ServiceFabricClusterPackage](./Copy-ServiceFabricClusterPackage.md)
Copies a Service Fabric cluster package to the image store.


### [Copy-ServiceFabricServicePackageToNode](./Copy-ServiceFabricServicePackageToNode.md)
Copies a service package to a target node.


### [Disable-ServiceFabricNode](./Disable-ServiceFabricNode.md)
Disables a Service Fabric node.


### [Enable-ServiceFabricNode](./Enable-ServiceFabricNode.md)
Enables a Service Fabric node.


### [Get-ServiceFabricApplicationHealth](./Get-ServiceFabricApplicationHealth.md)
Gets the health of a Service Fabric application.


### [Get-ServiceFabricApplicationLoadInformation](./Get-ServiceFabricApplicationLoadInformation.md)
Gets application capacity parameters and load information for a Service Fabric application.


### [Get-ServiceFabricApplicationManifest](./Get-ServiceFabricApplicationManifest.md)
Gets the manifest for a Service Fabric application type.


### [Get-ServiceFabricApplicationType](./Get-ServiceFabricApplicationType.md)
Gets the Service Fabric application types registered on the Service Fabric cluster.


### [Get-ServiceFabricApplicationUpgrade](./Get-ServiceFabricApplicationUpgrade.md)
Gets the status of a Service Fabric application upgrade.


### [Get-ServiceFabricApplication](./Get-ServiceFabricApplication.md)
Gets the Service Fabric applications in the Service Fabric cluster.


### [Get-ServiceFabricChaosReport](./Get-ServiceFabricChaosReport.md)
Gets a report of Chaos results.


### [Get-ServiceFabricClusterConfigurationUpgradeStatus](./Get-ServiceFabricClusterConfigurationUpgradeStatus.md)
Gets configuration upgrade status.


### [Get-ServiceFabricClusterConfiguration](./Get-ServiceFabricClusterConfiguration.md)
Gets the latest JSON cluster configuration.


### [Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
Gets the current Service Fabric cluster connection.


### [Get-ServiceFabricClusterHealthChunk](./Get-ServiceFabricClusterHealthChunk.md)
Gets health information for a Service Fabric cluster and its children.


### [Get-ServiceFabricClusterHealth](./Get-ServiceFabricClusterHealth.md)
Gets health information for a Service Fabric cluster.


### [Get-ServiceFabricClusterLoadInformation](./Get-ServiceFabricClusterLoadInformation.md)
Gets the load reports of a Service Fabric cluster.


### [Get-ServiceFabricClusterManifest](./Get-ServiceFabricClusterManifest.md)
Gets the Service Fabric cluster manifest.


### [Get-ServiceFabricClusterUpgrade](./Get-ServiceFabricClusterUpgrade.md)
Gets the status of a Service Fabric cluster upgrade.


### [Get-ServiceFabricDeployedApplicationHealth](./Get-ServiceFabricDeployedApplicationHealth.md)
Gets the health of a Service Fabric application on a node.


### [Get-ServiceFabricDeployedApplication](./Get-ServiceFabricDeployedApplication.md)
Gets a Service Fabric application on a node.


### [Get-ServiceFabricDeployedCodePackage](./Get-ServiceFabricDeployedCodePackage.md)
Gets the Service Fabric code packages deployed on a node.


### [Get-ServiceFabricDeployedReplicaDetail](./Get-ServiceFabricDeployedReplicaDetail.md)
Gets information about Service Fabric replicas from a host process.


### [Get-ServiceFabricDeployedReplica](./Get-ServiceFabricDeployedReplica.md)
Gets a Service Fabric replica on a node.


### [Get-ServiceFabricDeployedServicePackageHealth](./Get-ServiceFabricDeployedServicePackageHealth.md)
Gets the health of a Service Fabric service package.


### [Get-ServiceFabricDeployedServicePackage](./Get-ServiceFabricDeployedServicePackage.md)
Gets the Service Fabric service packages on a node.


### [Get-ServiceFabricDeployedServiceType](./Get-ServiceFabricDeployedServiceType.md)
Gets the Service Fabric service types deployed on a node.


### [Get-ServiceFabricImageStoreContent](./Get-ServiceFabricImageStoreContent.md)
Gets content from the image store.


### [Get-ServiceFabricNodeConfiguration](./Get-ServiceFabricNodeConfiguration.md)
Gets the configuration of a Service Fabric node.


### [Get-ServiceFabricNodeHealth](./Get-ServiceFabricNodeHealth.md)
Gets the health state of a Service Fabric node.


### [Get-ServiceFabricNodeLoadInformation](./Get-ServiceFabricNodeLoadInformation.md)
Gets detailed metrics load information for a Service Fabric node.


### [Get-ServiceFabricNode](./Get-ServiceFabricNode.md)
Gets information about the Service Fabric nodes in a cluster.


### [Get-ServiceFabricNodeTransitionProgress](./Get-ServiceFabricNodeTransitionProgress.md) 
Gets the progress of a node transition operation.


### [Get-ServiceFabricPartitionDataLossProgress](./Get-ServiceFabricPartitionDataLossProgress.md)
Gets the progress of a data loss operation.


### [Get-ServiceFabricPartitionHealth](./Get-ServiceFabricPartitionHealth.md)
Gets the health of a Service Fabric partition.


### [Get-ServiceFabricPartitionLoadInformation](./Get-ServiceFabricPartitionLoadInformation.md)
Gets the load reports for a Service Fabric partition.


### [Get-ServiceFabricPartitionQuorumLossProgress](./Get-ServiceFabricPartitionQuorumLossProgress.md)
Gets the progress of a quorum loss operation.


### [Get-ServiceFabricPartitionRestartProgress](./Get-ServiceFabricPartitionRestartProgress.md)
Gets the progress of a partition restart.


### [Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md)
Gets Service Fabric partitions.


### [Get-ServiceFabricRegisteredClusterCodeVersion](./Get-ServiceFabricRegisteredClusterCodeVersion.md)
Gets all provisioned fabric code versions in a Service Fabric cluster.


### [Get-ServiceFabricRegisteredClusterConfigVersion](./Get-ServiceFabricRegisteredClusterConfigVersion.md)
Gets provisioned fabric config versions in a Service Fabric cluster.


### [Get-ServiceFabricRepairTask](./Get-ServiceFabricRepairTask.md)
Gets the repair tasks.


### [Get-ServiceFabricReplicaHealth](./Get-ServiceFabricReplicaHealth.md)
Gets the health of a Service Fabric replica.


### [Get-ServiceFabricReplicaLoadInformation](./Get-ServiceFabricReplicaLoadInformation.md)
Gets detailed metrics load information for a Service Fabric replica.


### [Get-ServiceFabricReplica](./Get-ServiceFabricReplica.md)
Gets Service Fabric replicas.


### [Get-ServiceFabricServiceDescription](./Get-ServiceFabricServiceDescription.md)
Gets the Service Fabric service description of a service that is running.


### [Get-ServiceFabricServiceGroupDescription](./Get-ServiceFabricServiceGroupDescription.md)
Gets a Service Fabric service group description.


### [Get-ServiceFabricServiceGroupMemberType](./Get-ServiceFabricServiceGroupMemberType.md)
Gets member types of Service Fabric service groups.


### [Get-ServiceFabricServiceGroupMember](./Get-ServiceFabricServiceGroupMember.md)
Gets members of service groups.


### [Get-ServiceFabricServiceHealth](./Get-ServiceFabricServiceHealth.md)
Gets the health of a Service Fabric service.


### [Get-ServiceFabricServiceManifest](./Get-ServiceFabricServiceManifest.md)
Gets the Service Fabric service type manifest.


### [Get-ServiceFabricServiceType](./Get-ServiceFabricServiceType.md)
Gets Service Fabric service types.


### [Get-ServiceFabricService](./Get-ServiceFabricService.md)
Gets a list of Service Fabric services.


### [Get-ServiceFabricTestCommandStatusList](./Get-ServiceFabricTestCommandStatusList.md)
Gets test commands.


### [Invoke-ServiceFabricChaosTestScenario](./Invoke-ServiceFabricChaosTestScenario.md)
Invokes a test scenario to induce iterative failover and faults in a cluster.


### [Invoke-ServiceFabricDecryptText](./Invoke-ServiceFabricDecryptText.md)
Decrypts text for verification.


### [Invoke-ServiceFabricEncryptSecret](./Invoke-ServiceFabricEncryptSecret.md)
Encrypts text in the cluster manifest by using a certificate.


### [Invoke-ServiceFabricEncryptText](./Invoke-ServiceFabricEncryptText.md)
Encrypts secrets to include in Service Fabric manifests or configurations.


### [Invoke-ServiceFabricFailoverTestScenario](./Invoke-ServiceFabricFailoverTestScenario.md)
Invokes a test scenario to induce faults in a Service Fabric partition.


### [Invoke-ServiceFabricInfrastructureCommand](./Invoke-ServiceFabricInfrastructureCommand.md)
Invokes an administrative command on an infrastructure service.


### [Invoke-ServiceFabricInfrastructureQuery](./Invoke-ServiceFabricInfrastructureQuery.md)
Invokes a read-only query on an infrastructure service.


### [Invoke-ServiceFabricPartitionDataLoss](./Invoke-ServiceFabricPartitionDataLoss.md)
Invokes an action to induce data loss for a Service Fabric partition.


### [Invoke-ServiceFabricPartitionQuorumLoss](./Invoke-ServiceFabricPartitionQuorumLoss.md)
Invokes an action to induce quorum loss in a Service Fabric partition.


### [Move-ServiceFabricPrimaryReplica](./Move-ServiceFabricPrimaryReplica.md)
Moves the Service Fabric primary replica of a stateful service partition.


### [Move-ServiceFabricSecondaryReplica](./Move-ServiceFabricSecondaryReplica.md)
Moves the Service Fabric secondary replica of a stateful service.


### [New-ServiceFabricApplication](./New-ServiceFabricApplication.md)
Creates a Service Fabric application.


### [New-ServiceFabricCluster](./New-ServiceFabricCluster.md)
Creates a Service Fabric cluster.


### [New-ServiceFabricNodeConfiguration](./New-ServiceFabricNodeConfiguration.md)
Configures a node to join a Service Fabric cluster.


### [New-ServiceFabricPackageDebugParameter](./New-ServiceFabricPackageDebugParameter.md)
Adds debug parameters for a code package in a service package.


### [New-ServiceFabricPackageSharingPolicy](./New-ServiceFabricPackageSharingPolicy.md)
Creates a package sharing policy.


### [New-ServiceFabricServiceFromTemplate](./New-ServiceFabricServiceFromTemplate.md)
Creates a Service Fabric service from the service template defined in the application manifest.


### [New-ServiceFabricServiceGroupFromTemplate](./New-ServiceFabricServiceGroupFromTemplate.md)
Creates a Service Fabric service group from a service template.


### [New-ServiceFabricServiceGroup](./New-ServiceFabricServiceGroup.md)
Creates a Service Fabric service group.


### [New-ServiceFabricService](./New-ServiceFabricService.md)
Creates a Service Fabric service.


### [Register-ServiceFabricApplicationType](./Register-ServiceFabricApplicationType.md)
Registers a Service Fabric application type.


### [Register-ServiceFabricClusterPackage](./Register-ServiceFabricClusterPackage.md)
Registers a Service Fabric cluster package.


### [Remove-ServiceFabricApplicationPackage](./Remove-ServiceFabricApplicationPackage.md)
Removes a Service Fabric application package from the image store.


### [Remove-ServiceFabricApplication](./Remove-ServiceFabricApplication.md)
Removes a Service Fabric application.


### [Remove-ServiceFabricClusterPackage](./Remove-ServiceFabricClusterPackage.md)
Removes a Service Fabric cluster package from the image store.


### [Remove-ServiceFabricCluster](./Remove-ServiceFabricCluster.md)
Removes a Service Fabric cluster.


### [Remove-ServiceFabricNodeConfiguration](./Remove-ServiceFabricNodeConfiguration.md)
Removes information related to a configured node.


### [Remove-ServiceFabricNodeState](./Remove-ServiceFabricNodeState.md)
Notifies Service Fabric that the state on a node has been removed by an external mechanism.


### [Remove-ServiceFabricNode](./Remove-ServiceFabricNode.md)
Removes a Service Fabric node.


### [Remove-ServiceFabricRepairTask](./Remove-ServiceFabricRepairTask.md)
Deletes a completed repair task.


### [Remove-ServiceFabricReplica](./Remove-ServiceFabricReplica.md)
Removes a replica from a cluster to simulate a replica failure.


### [Remove-ServiceFabricServiceGroup](./Remove-ServiceFabricServiceGroup.md)
Removes a Service Fabric service group.


### [Remove-ServiceFabricService](./Remove-ServiceFabricService.md)
Removes an existing Service Fabric service.


### [Remove-ServiceFabricTestState](./Remove-ServiceFabricTestState.md)
Removes all test state data from a Service Fabric cluster.


### [Repair-ServiceFabricPartition](./Repair-ServiceFabricPartition.md)
Brings a partition out of quorum loss.


### [Reset-ServiceFabricPartitionLoad](./Reset-ServiceFabricPartitionLoad.md)
Resets the current load of a Service Fabric partition.


### [Resolve-ServiceFabricService](./Resolve-ServiceFabricService.md)
Retrieves the replica or instance address of a Service Fabric service.


### [Restart-ServiceFabricDeployedCodePackage](./Restart-ServiceFabricDeployedCodePackage.md)
Restarts a code package deployed on a node in a cluster to simulate a process failure.


### [Restart-ServiceFabricNode](./Restart-ServiceFabricNode.md)
Restarts a Service Fabric node to simulate a cluster node failure.


### [Restart-ServiceFabricPartition](./Restart-ServiceFabricPartition.md)
Restarts replicas of a Service Fabric partition to simulate a data center blackout or cluster blackout scenario.


### [Restart-ServiceFabricReplica](./Restart-ServiceFabricReplica.md)
Restarts a Service Fabric replica.


### [Resume-ServiceFabricApplicationUpgrade](./Resume-ServiceFabricApplicationUpgrade.md)
Resumes an unmonitored Service Fabric application upgrade.


### [Resume-ServiceFabricClusterUpgrade](./Resume-ServiceFabricClusterUpgrade.md)
Resumes an unmonitored Service Fabric cluster upgrade.


### [Send-ServiceFabricApplicationHealthReport](./Send-ServiceFabricApplicationHealthReport.md)
Sends a health report on a Service Fabric application.


### [Send-ServiceFabricClusterHealthReport](./Send-ServiceFabricClusterHealthReport.md)
Sends a health report on a Service Fabric cluster.


### [Send-ServiceFabricDeployedApplicationHealthReport](./Send-ServiceFabricDeployedApplicationHealthReport.md)
Sends a health report on a Service Fabric application deployed on a node.


### [Send-ServiceFabricDeployedServicePackageHealthReport](./Send-ServiceFabricDeployedServicePackageHealthReport.md)
Sends a health report on a Service Fabric deployed service package.


### [Send-ServiceFabricNodeHealthReport](./Send-ServiceFabricNodeHealthReport.md)
Sends a health report on a Service Fabric node.


### [Send-ServiceFabricPartitionHealthReport](./Send-ServiceFabricPartitionHealthReport.md)
Sends a health report on a Service Fabric service partition.


### [Send-ServiceFabricReplicaHealthReport](./Send-ServiceFabricReplicaHealthReport.md)
Sends a health report on a Service Fabric replica.


### [Send-ServiceFabricServiceHealthReport](./Send-ServiceFabricServiceHealthReport.md)
Sends a health report on a Service Fabric service.


### [Start-ServiceFabricApplicationRollback](./Start-ServiceFabricApplicationRollback.md)
Starts rolling back a Service Fabric application upgrade.


### [Start-ServiceFabricApplicationUpgrade](./Start-ServiceFabricApplicationUpgrade.md)
Upgrades a Service Fabric application.


### [Start-ServiceFabricChaos](./Start-ServiceFabricChaos.md)
Starts Chaos in the cluster as part of FAS.


### [Start-ServiceFabricClusterConfigurationUpgrade](./Start-ServiceFabricClusterConfigurationUpgrade.md)
Upgrades a cluster configuration.


### [Start-ServiceFabricClusterRollback](./Start-ServiceFabricClusterRollback.md)
Starts rolling back a Service Fabric cluster upgrade.


### [Start-ServiceFabricClusterUpgrade](./Start-ServiceFabricClusterUpgrade.md)
Upgrades a Service Fabric cluster.


### [Start-ServiceFabricNode](./Start-ServiceFabricNode.md)
Starts a Service Fabric node.


### [Start-ServiceFabricNodeTransition](./Start-ServiceFabricNodeTransition.md)
Initiates an operation to start or stop a Service Fabric node.


### [Start-ServiceFabricPartitionDataLoss](./Start-ServiceFabricPartitionDataLoss.md)
Starts to perform a data loss test on a partition.


### [Start-ServiceFabricPartitionQuorumLoss](./Start-ServiceFabricPartitionQuorumLoss.md)
Initiates an operation to put a partition into quorum loss.


### [Start-ServiceFabricPartitionRestart](./Start-ServiceFabricPartitionRestart.md)
Initiates the restart of a stateful service partition.


### [Start-ServiceFabricRepairTask](./Start-ServiceFabricRepairTask.md)
Creates a repair task.


### [Stop-ServiceFabricChaos](./Stop-ServiceFabricChaos.md)
Stops Chaos in the cluster.


### [Stop-ServiceFabricNode](./Stop-ServiceFabricNode.md)
Stops a Service Fabric node.


### [Stop-ServiceFabricRepairTask](./Stop-ServiceFabricRepairTask.md)
Cancels a repair task.


### [Stop-ServiceFabricTestCommand](./Stop-ServiceFabricTestCommand.md)
Cancels a Service Fabric test command.


### [Test-ServiceFabricApplicationPackage](./Test-ServiceFabricApplicationPackage.md)
Validates a Service Fabric application package.


### [Test-ServiceFabricApplication](./Test-ServiceFabricApplication.md)
Validates a Service Fabric application.


### [Test-ServiceFabricClusterConnection](./Test-ServiceFabricClusterConnection.md)
Validates the current connection to a Service Fabric cluster.


### [Test-ServiceFabricClusterManifest](./Test-ServiceFabricClusterManifest.md)
Validates a Service Fabric cluster manifest.


### [Test-ServiceFabricConfiguration](./Test-ServiceFabricConfiguration.md)
Validates cluster configuration and tests whether deployment can succeed.


### [Test-ServiceFabricService](./Test-ServiceFabricService.md)
Validates a Service Fabric service.


### [Unregister-ServiceFabricApplicationType](./Unregister-ServiceFabricApplicationType.md)
Unregisters a Service Fabric application type.


### [Unregister-ServiceFabricClusterPackage](./Unregister-ServiceFabricClusterPackage.md)
Unregisters a Service Fabric cluster package.


### [Update-ServiceFabricApplicationUpgrade](./Update-ServiceFabricApplicationUpgrade.md)
Modifies the upgrade description of an active Application upgrade.


### [Update-ServiceFabricApplication](./Update-ServiceFabricApplication.md)
Updates or removes application capacity.


### [Update-ServiceFabricClusterUpgrade](./Update-ServiceFabricClusterUpgrade.md)
Modifies the upgrade description of an active Cluster upgrade.


### [Update-ServiceFabricNodeConfiguration](./Update-ServiceFabricNodeConfiguration.md)
Updates a Service Fabric cluster configuration.


### [Update-ServiceFabricRepairTaskHealthPolicy](./Update-ServiceFabricRepairTaskHealthPolicy.md) 
Updates the health policy of a repair task.


### [Update-ServiceFabricServiceGroup](./Update-ServiceFabricServiceGroup.md)
Updates a Service Fabric service group.


### [Update-ServiceFabricService](./Update-ServiceFabricService.md)
Updates a Service Fabric service.
