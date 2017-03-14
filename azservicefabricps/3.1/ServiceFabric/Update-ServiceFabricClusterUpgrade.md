---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 19517C43-639C-4FB0-8BEE-5B751DC5CBE5
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Update-ServiceFabricClusterUpgrade.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Update-ServiceFabricClusterUpgrade.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Update-ServiceFabricClusterUpgrade

## SYNOPSIS
Modifies the upgrade description of an active Cluster upgrade.

## SYNTAX

```
Update-ServiceFabricClusterUpgrade [-ForceRestart <Boolean>] [-UpgradeReplicaSetCheckTimeoutSec <UInt32>]
 [-UpgradeMode <RollingUpgradeMode>] [-FailureAction <UpgradeFailureAction>]
 [-HealthCheckRetryTimeoutSec <UInt32>] [-HealthCheckWaitDurationSec <UInt32>]
 [-HealthCheckStableDurationSec <UInt32>] [-UpgradeDomainTimeoutSec <UInt32>] [-UpgradeTimeoutSec <UInt32>]
 [-ConsiderWarningAsError <Boolean>] [-MaxPercentUnhealthyApplications <Byte>]
 [-MaxPercentUnhealthyNodes <Byte>] [-ApplicationTypeHealthPolicyMap <ApplicationTypeHealthPolicyMap>]
 [-EnableDeltaHealthEvaluation <Boolean>] [-MaxPercentDeltaUnhealthyNodes <Byte>]
 [-MaxPercentUpgradeDomainDeltaUnhealthyNodes <Byte>] [-Force]
 [-ApplicationHealthPolicyMap <ApplicationHealthPolicyMap>] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-ServiceFabricClusterUpgrade** cmdlet modifies the parameters of a cluster upgrade description while the upgrade is still active.
Service Fabric detects and applies the changes according to the **FabricUpgradeStatusPollInterval** value, as specified in the cluster manifest.
Except for health-evaluation policies, this cmdlet updates only the parameters that you specify.
Unspecified parameters remain unaffected.
You must update the following health-evaluation policies together, not individually:

- *ConsiderWarningAsError*
- *MaxPercentUnhealthyApplications*
- *MaxPercentUnhealthyNodes*

To manage Service Fabric clusters, start Windows PowerShell by using the Run as administrator option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Update a value for a cluster upgrade
```
PS C:\>Update-ServiceFabricClusterUpgrade -UpgradeReplicaSetCheckTimeoutSec 0
```

This command sets the replica set check time-out period to 0 for a pending cluster upgrade.
The update leaves all other upgrade values alone.

### Example 2: Update health policy for a cluster upgrade
```
PS C:\>$svcType = New-Object -TypeName System.Fabric.Health.ServiceTypeHealthPolicy
PS C:\> $svcType.MaxPercentUnhealthyPartitionsPerService = 100
PS C:\> $systemAppPolicy = New-Object -TypeName System.Fabric.Health.ApplicationHealthPolicy
PS C:\> $systemAppPolicy.DefaultServiceTypeHealthPolicy = $svcType
PS C:\> $appHealthPolicyMap = New-Object -TypeName System.Fabric.Health.ApplicationHealthPolicyMap
PS C:\> $appHealthPolicyMap.Add("fabric:/System", $systemAppPolicy)

PS C:\> $AppTypeHealthPolicyMap = New-Object -TypeName "System.Fabric.Health.ApplicationTypeHealthPolicyMap"
PS C:\> $AppTypeHealthPolicyMap.Add("CriticalAppType", 0)

PS C:\> Update-ServiceFabricClusterUpgrade -ApplicationTypeHealthPolicyMap $AppTypeHealthPolicyMap -Force -MaxPercentUnhealthyApplications 20 -ApplicationHealthPolicyMap $appHealthPolicyMap
```

This command changes the cluster upgrade cluster health policy.
It specifies the application type health policy map that contains the application type CriticalAppType, which does not tolerate any failures.
The rest of the applications are evaluated using 20% maximum percent unhealthy.

The command also updates the application health policy used to evaluate fabric:/System application as part of the cluster upgrade health evaluation.
The new policies tolerate all partition errors.

## PARAMETERS

### -ApplicationHealthPolicyMap
Specifies a **System.Fabric.Health.ApplicationHealthPolicyMap** that includes custom health policies for some or all of the applications.
If you do not specify this parameter, or if you don't include an entry in the map for an application, that application is evaluated with the application health policy defined in the application manifest if it exists, or the default policy otherwise.

```yaml
Type: ApplicationHealthPolicyMap
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeHealthPolicyMap
Specifies the map that defines the maximum percentage of unhealthy applications that are allowed per application type.
Application types in this map are evaluated using specific percentages rather than the global *MaxPercentUnhealthyApplications* percentage.

For example, if some applications of a type are critical, the cluster administrator can add an entry to the map for that application type and assign it a value of 0% (that is, do not tolerate any failures).
All other applications can be evaluated with *MaxPercentUnhealthyApplications* set to 20% to tolerate some failures out of the thousands of application instances.

The application type health policy map is used only if the cluster manifest enables application type health evaluation using the configuration entry for **HealthManager/EnableApplicationTypeHealthEvaluation**.

```yaml
Type: ApplicationTypeHealthPolicyMap
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -EnableDeltaHealthEvaluation
Indicates whether to enable delta health checks during health evaluation in monitored upgrades.
If you specify a value of $True, Service Fabric takes a snapshot of the health at the beginning of the upgrade.
After each upgrade domain finishes the upgrade, the health checks compare current state of the cluster with the snapshot.
If there is health degradation that does not respect maximum allow percentages from current cluster upgrade health policy, the health checks fail.

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

### -FailureAction
Specifies the action to take if the monitored upgrade fails.
The acceptable values for this parameter are:

- Rollback
- Manual.

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
Indicates whether to restart the Service Fabric node even if only dynamic configurations have changed.

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
Specifies the duration, in seconds, that Service Fabric waits in order to verify that the cluster is stable before it continues to the next upgrade domain or completes the upgrade.
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

### -MaxPercentDeltaUnhealthyNodes
Specifies the maximum tolerated percentage of delta unhealthy nodes that can have aggregated health states of error.
If the current unhealthy nodes do not respect the percentage relative to the state at the beginning of the upgrade, the cluster is unhealthy.

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

### -MaxPercentUnhealthyApplications
Specifies the maximum tolerated percentage of applications that can have aggregated health state of error.
If the upgrade exceeds this percentage, the cluster is unhealthy.

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

### -MaxPercentUnhealthyNodes
Specifies the maximum tolerated percentage of nodes that can have aggregated health states of error.
If an upgrade exceeds this percentage, the cluster is unhealthy.

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

### -MaxPercentUpgradeDomainDeltaUnhealthyNodes
Specifies the maximum tolerated percentage of upgrade domain delta unhealthy nodes that can have aggregated health state of error.
If there is any upgrade domain where the current unhealthy nodes do not respect the percentage relative to the state at the beginning of the upgrade, the cluster is unhealthy.

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
Specifies the maximum time, in seconds, that Service Fabric waits for a replica set to reconfigure into a safe state, if it is not already in a safe state, before Service Fabric proceeds with the upgrade.

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
This cmdlet returns a **System.Fabric.Description.FabricUpgradeUpdateDescription** object that describes the applied upgrade update parameters.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricClusterUpgrade](./Get-ServiceFabricClusterUpgrade.md)

[Resume-ServiceFabricClusterUpgrade](./Resume-ServiceFabricClusterUpgrade.md)

[Start-ServiceFabricClusterUpgrade](./Start-ServiceFabricClusterUpgrade.md)

[Update-ServiceFabricApplicationUpgrade](./Update-ServiceFabricApplicationUpgrade.md)
