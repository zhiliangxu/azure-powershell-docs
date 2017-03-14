---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: DAE0CBD7-0E5B-4F46-B8AB-68065C68802D
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Update-ServiceFabricApplicationUpgrade.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Update-ServiceFabricApplicationUpgrade.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Update-ServiceFabricApplicationUpgrade

## SYNOPSIS
Modifies the upgrade description of an active Application upgrade.

## SYNTAX

```
Update-ServiceFabricApplicationUpgrade [-ApplicationName] <Uri> [-ForceRestart <Boolean>]
 [-UpgradeReplicaSetCheckTimeoutSec <UInt32>] [-UpgradeMode <RollingUpgradeMode>]
 [-FailureAction <UpgradeFailureAction>] [-HealthCheckRetryTimeoutSec <UInt32>]
 [-HealthCheckWaitDurationSec <UInt32>] [-HealthCheckStableDurationSec <UInt32>]
 [-UpgradeDomainTimeoutSec <UInt32>] [-UpgradeTimeoutSec <UInt32>] [-ConsiderWarningAsError <Boolean>]
 [-DefaultServiceTypeHealthPolicy <String>] [-MaxPercentUnhealthyDeployedApplications <Byte>]
 [-ServiceTypeHealthPolicyMap <Hashtable>] [-Force] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-ServiceFabricApplicationUpgrade** cmdlet modifies the parameters of an Application upgrade description while the upgrade is still active.
Service Fabric detects and applies changes according to the **UpgradeStatusPollInterval** value, as specified in the cluster manifest.
Except for health-evaluation policies, this cmdlet updates only the parameters that you specify.
Unspecified parameters remain unaffected.
You must update the following health-evaluation policies together, not individually:

- *ConsiderWarningAsError*
- *DefaultServiceTypeHealthPolicy*
- *MaxPercentUnhealthyDeployedApplications*
- *ServiceTypeHealthPolicyMap*

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Update a value for an application upgrade
```
PS C:\>Update-ServiceFabricApplicationUpgrade -ApplicationName fabric:/MyApplication -UpgradeReplicaSetCheckTimeoutSec 0
```

This command sets the replica set check time-out value to 0 for a pending upgrade on fabric:/MyApplication.
The update leaves all other upgrade values alone.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet updates the settings for the upgrade for the application that has the URI that this parameter specifies.

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
Indicates whether to treat a warning health report as error during health evaluation.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultServiceTypeHealthPolicy
Specifies the default health policy for service types.
Health policy is used for the monitored upgrade.
The policy follows the format MaxPercentUnhealthyPartitionsPerService,MaxPercentUnhealthyReplicasPerPartition,MaxPercentUnhealthyServices.
For example, 5,10,15 indicates the following values:

- MaxPercentUnhealthyPartitionsPerService = 5
- MaxPercentUnhealthyReplicasPerPartition = 10
- MaxPercentUnhealthyServices = 15

```yaml
Type: String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, Rollback, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet skips the warning message and forces the update.

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
Indicates whether the service host restarts even if the upgrade is a configuration-only change.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthCheckRetryTimeoutSec
Specifies the duration, in seconds, after which Service Fabric retries the health check if the previous health check fails.

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

### -HealthCheckStableDurationSec
Specifies the duration, in seconds, that Service Fabric waits in order to verify that the application is stable before it continues to the next upgrade domain or completes the upgrade.
This wait duration prevents undetected changes of health right after the health check is performed.

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

### -HealthCheckWaitDurationSec
Specifies the duration, in seconds, that Service Fabric waits before it performs the initial health check after it finishes the upgrade on the upgrade domain.

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

### -MaxPercentUnhealthyDeployedApplications
Specifies the maximum percentage of tolerated deployed applications that can have a health state of error.
If the percentage of unhealthy application instances deployed on the nodes in the cluster exceeds the value that this parameter specifies, the health state of the application is error.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceTypeHealthPolicyMap
Specifies the map of the health policy to use for different service types.
Specify the map as a hash table in the following format: @ {"*ServiceTypeName*" : "MaxPercentUnhealthyPartitionsPerService,MaxPercentUnhealthyReplicasPerPartition,MaxPercentUnhealthyServices"}.
For instance:

@{ "ServiceTypeName01" = "5,10,5"; "ServiceTypeName02" = "5,5,5" }

```yaml
Type: Hashtable
Parameter Sets: (All)
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

### -UpgradeDomainTimeoutSec
Specifies the maximum time, in seconds, that Service Fabric takes to upgrade a single upgrade domain.
After this period, the upgrade fails.

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

### -UpgradeMode
Specifies the new **UpgradeMode** for the upgrade.

```yaml
Type: RollingUpgradeMode
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, UnmonitoredAuto, UnmonitoredManual, Monitored

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeReplicaSetCheckTimeoutSec
Specifies the maximum time, in seconds, that Service Fabric waits for a service to reconfigure into a safe state, if not already in a safe state, before Service Fabric proceeds with the upgrade.

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

### -UpgradeTimeoutSec
Specifies the maximum time, in seconds, that Service Fabric takes for the entire upgrade.
After this period, the upgrade fails.

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
This cmdlet returns a **System.Fabric.Description.ApplicationUpgradeUpdateDescription** object.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricApplicationUpgrade](./Get-ServiceFabricApplicationUpgrade.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Resume-ServiceFabricApplicationUpgrade](./Resume-ServiceFabricApplicationUpgrade.md)

[Start-ServiceFabricApplicationUpgrade](./Start-ServiceFabricApplicationUpgrade.md)

[Update-ServiceFabricClusterUpgrade](./Update-ServiceFabricClusterUpgrade.md)
