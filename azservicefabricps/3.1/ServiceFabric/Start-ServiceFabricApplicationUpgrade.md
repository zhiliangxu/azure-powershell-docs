---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 9C765157-6B48-4AC8-A4D5-C26C098CFC17
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricApplicationUpgrade.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricApplicationUpgrade.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Start-ServiceFabricApplicationUpgrade

## SYNOPSIS
Upgrades a Service Fabric application.

## SYNTAX

### UnmonitoredAuto (Default)
```
Start-ServiceFabricApplicationUpgrade [-ApplicationName] <Uri> [-ApplicationTypeVersion] <String>
 [[-ApplicationParameter] <Hashtable>] [-ForceRestart] [[-UpgradeReplicaSetCheckTimeoutSec] <UInt32>]
 [-ReplicaQuorumTimeoutSec <UInt32>] [-RestartProcess] [-UnmonitoredAuto] [-Force] [-TimeoutSec <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UnmonitoredManual
```
Start-ServiceFabricApplicationUpgrade [-ApplicationName] <Uri> [-ApplicationTypeVersion] <String>
 [[-ApplicationParameter] <Hashtable>] [-ForceRestart] [[-UpgradeReplicaSetCheckTimeoutSec] <UInt32>]
 [-ReplicaQuorumTimeoutSec <UInt32>] [-RestartProcess] [-UnmonitoredManual] [-Force] [-TimeoutSec <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Monitored
```
Start-ServiceFabricApplicationUpgrade [-ApplicationName] <Uri> [-ApplicationTypeVersion] <String>
 [[-ApplicationParameter] <Hashtable>] [-ForceRestart] [[-UpgradeReplicaSetCheckTimeoutSec] <UInt32>]
 [-ReplicaQuorumTimeoutSec <UInt32>] [-RestartProcess] [-Monitored] -FailureAction <UpgradeFailureAction>
 [-HealthCheckRetryTimeoutSec <UInt32>] [-HealthCheckWaitDurationSec <UInt32>]
 [-HealthCheckStableDurationSec <UInt32>] [-UpgradeDomainTimeoutSec <UInt32>] [-UpgradeTimeoutSec <UInt32>]
 [-ConsiderWarningAsError <Boolean>] [-DefaultServiceTypeHealthPolicy <String>]
 [-MaxPercentUnhealthyDeployedApplications <Byte>] [-ServiceTypeHealthPolicyMap <Hashtable>] [-Force]
 [-TimeoutSec <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-ServiceFabricApplicationUpgrade** cmdlet upgrades a Service Fabric application.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Upgrade an application
```
PS C:\>Copy-ServiceFabricApplicationPackage -ApplicationPackagePath "C:\PersistentToDoListServiceV2" -ImageStoreConnectionString "file:C:\ProgramData\ServiceFabric\ImageStore"
PS C:\> Register-ServiceFabricApplicationType -ApplicationPathInImageStore "PersistentToDoListServiceV2"
PS C:\> Start-ServiceFabricApplicationUpgrade -ApplicationName fabric:/myapp/persistenttodolist -ApplicationTypeVersion "2.0" -RestartProcess -UnMonitoredManual
```

The first command uses the [Copy-ServiceFabricApplicationPackage](./Copy-ServiceFabricApplicationPackage.md) cmdlet to copy the updated application package to the image store.

The second command uses the [Register-ServiceFabricApplicationType](./Register-ServiceFabricApplicationType) cmdlet to register the updated application type.

The final command upgrades the application.
The command performs an unmonitored manual upgrade, which includes a restart of the server that hosts the application.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet upgrades the application that has the URI that you specify.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationParameter
Specifies the overrides for application parameters as name/value pairs.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeVersion
Specifies the version of a Service Fabric application type.
The cmdlet upgrades the application to the version that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsiderWarningAsError
Indicates whether to treat a warning health event as an error event during health evaluation.

```yaml
Type: Boolean
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultServiceTypeHealthPolicy
Specifies the health policy for the default service type to use for the monitored upgrade in the format MaxPercentUnhealthyPartitionsPerService, MaxPercentUnhealthyReplicasPerPartition, MaxPercentUnhealthyServices.
For example, 5,10,15 indicates the following values:

- MaxPercentUnhealthyPartitionsPerService = 5
- MaxPercentUnhealthyReplicasPerPartition = 10
- MaxPercentUnhealthyServices = 15

```yaml
Type: String
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailureAction
Specifies the action to take if the monitored upgrade fails.
The acceptable values for this parameter are:

- Rollback
- Manual

```yaml
Type: UpgradeFailureAction
Parameter Sets: Monitored
Aliases:
Accepted values: Invalid, Rollback, Manual

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet skips the warning message and forces the upgrade.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceRestart
Indicates that the service host restarts even if the upgrade is a configuration-only change.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthCheckRetryTimeoutSec
Specifies the duration, in seconds, after which Service Fabric retries the health check if the previous health check fails.

```yaml
Type: UInt32
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthCheckStableDurationSec
Specifies the duration, in seconds, that Service Fabric waits in order to verify that the application is stable before moving to the next upgrade domain or completing the upgrade.
This wait duration prevents undetected changes of health right after the health check is performed.

```yaml
Type: UInt32
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthCheckWaitDurationSec
Specifies the duration, in seconds, that Service Fabric waits before it performs the initial health check after it finishes the upgrade on the upgrade domain.

```yaml
Type: UInt32
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPercentUnhealthyDeployedApplications
Specifies the maximum percentage of the application instances deployed on the nodes in the cluster that have a health state of error before the application health state for the cluster is error.

```yaml
Type: Byte
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Monitored
Indicates that the upgrade mode is monitored.
After the cmdlet finishes an upgrade for an upgrade domain, if the health of the upgrade domain and the cluster meet the health policies that you define, Service Fabric upgrades the next upgrade domain.
If the upgrade domain or cluster fails to meet health policies, the upgrade fails and Service Fabric rolls back the upgrade for the upgrade domain or reverts to manual mode per the policy specified.
This is the recommended mode for application upgrades in a production environment.

```yaml
Type: SwitchParameter
Parameter Sets: Monitored
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaQuorumTimeoutSec
Specifies the time-out period, in seconds, to check whether the replica set has quorum.
After the time-out period, the upgrade proceeds.

This parameter has been deprecated.
Specify the *UpgradeReplicaSetCheckTimeoutSec* parameter instead.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartProcess
Indicates that the service host restarts as part of the upgrade.

This parameter has been deprecated.
Specify the *ForceRestart* parameter instead.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceTypeHealthPolicyMap
Specifies the map of the health policy to use for different service types as a hash table in the following format: @ {"*ServiceTypeName*" : "MaxPercentUnhealthyPartitionsPerService,MaxPercentUnhealthyReplicasPerPartition,MaxPercentUnhealthyServices"}.
For example:

@{ "ServiceTypeName01" = "5,10,5"; "ServiceTypeName02" = "5,5,5" }

```yaml
Type: Hashtable
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSec
Specifies the time-out period, in seconds, for the operation.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnmonitoredAuto
Indicates that the upgrade mode is unmonitored automatic.
After Service Fabric upgrades an upgrade domain, Service Fabric upgrades the next upgrade domain irrespective of the application health state.
This mode is not recommended for production, and is only useful during development of an application.

```yaml
Type: SwitchParameter
Parameter Sets: UnmonitoredAuto
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnmonitoredManual
Indicates that the upgrade mode is unmonitored manual.
After Service Fabric upgrades an upgrade domain, it waits for you to upgrade the next upgrade domain by using the [Resume-ServiceFabricApplicationUpgrade](./Resume-ServiceFabricApplicationUpgrade.md) cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: UnmonitoredManual
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeDomainTimeoutSec
Specifies the maximum time, in seconds, that Service Fabric takes to upgrade a single upgrade domain.
After this period, the upgrade fails.

```yaml
Type: UInt32
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeReplicaSetCheckTimeoutSec
Specifies the maximum time that Service Fabric waits for a service to reconfigure into a safe state, if not already in a safe state, before Service Fabric proceeds with the upgrade.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeTimeoutSec
Specifies the maximum time, in seconds, that Service Fabric takes for the entire upgrade.
After this period, the upgrade fails.

```yaml
Type: UInt32
Parameter Sets: Monitored
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Description.ApplicationUpgradeDescription** for a Service Fabric application upgrade.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricApplicationUpgrade](./Get-ServiceFabricApplicationUpgrade.md)

[Resume-ServiceFabricApplicationUpgrade](./Resume-ServiceFabricApplicationUpgrade.md)

[Copy-ServiceFabricApplicationPackage](./Copy-ServiceFabricApplicationPackage.md)

[Register-ServiceFabricApplicationType](./Register-ServiceFabricApplicationType.md)
