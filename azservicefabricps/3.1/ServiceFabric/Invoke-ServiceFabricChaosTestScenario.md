---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 9F010748-70B9-4E00-94C7-EBD0B2983C35
updated_at: 11/03/2016 08:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricChaosTestScenario.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricChaosTestScenario.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/1ee1eb862e0b78a20a656aad5e958efd0f11f85c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Invoke-ServiceFabricChaosTestScenario

## SYNOPSIS
Invokes a test scenario to induce iterative failover and faults in a cluster.

## SYNTAX

```
Invoke-ServiceFabricChaosTestScenario [-TimeToRunMinute] <UInt32> [-MaxClusterStabilizationTimeoutSec] <UInt32>
 [-WaitTimeBetweenIterationsSec <UInt32>] [-WaitTimeBetweenFaultsSec <UInt32>] [-MaxConcurrentFaults <UInt32>]
 [-EnableMoveReplicaFaults] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-ServiceFabricChaosTestScenario** cmdlet starts a test scenario to induce iterative failover and faults in a Service Fabric cluster.
The cmdlet validates the health and availability of all of the services in the cluster before starting the next iteration of failover and faults.
Use the *MaxConcurrentFaults* parameter to specify the maximum number of concurrent faults for each iteration.

If at any time a service is not healthy or is unavailable by the amount of time specified by the *MaxClusterStabilizationTimeout* parameter, the test fails with a FabricValidationException exception.

The faults are induced in a manner such that the faults do not cause any service or data to become unavailable; however, the chaos test scenario assumes no outside faults are induced or any unexpected failures occur, in which case services or data may become unavailable.

The **Invoke-ServiceFabricChaosTestScenario** cmdlet helps you to analyze your test or staging clusters to ensure that system faults do not result in loss of data availability or other unexpected service issues.

Before using this cmdlet, connect to the Service Fabric cluster.

## EXAMPLES

### Example 1: Run a chaos test
```
PS C:\>$TimeToRun = 60
PS C:\> $MaxStabilizationTimeSecs = 180
PS C:\> $ConcurrentFaults = 3
PS C:\> $WaitTimeBetweenIterationsSec = 60
PS C:\> Invoke-ServiceFabricChaosTestScenario -TimeToRunMinute $TimeToRun -MaxClusterStabilizationTimeoutSec $MaxStabilizationTimeSecs -MaxConcurrentFaults $ConcurrentFaults -EnableMoveReplicaFaults -WaitTimeBetweenIterationsSec $WaitTimeBetweenIterationsSec
```

The first four commands store values in variables to use as parameters.
The final command runs the chaos test for 60 minutes with a maximum stabilization time of 180 seconds and three maximum concurrent faults.

## PARAMETERS

### -EnableMoveReplicaFaults
Indicates that this cmdlet enables move replica faults.

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

### -MaxClusterStabilizationTimeoutSec
Specifies the maximum time-out period, in seconds, for a cluster to stabilize after a fault before failing the test.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxConcurrentFaults
Specifies the maximum number of concurrent faults.

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

### -TimeToRunMinute
Specifies the total time, in minutes, for the scenario to run.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

### -WaitTimeBetweenFaultsSec
Specifies the maximum wait time, in seconds, between consecutive faults.
The larger the value the lower the concurrency.

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

### -WaitTimeBetweenIterationsSec
Specifies the wait time, in seconds, for the duration between iterations.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### UInt32
Represents the time to run.

### UInt32
Represents the maximum stabilization time, in seconds, for the cluster.

## OUTPUTS

### System.Object
This cmdlet returns a **String** object that represents the final status of the test.

## NOTES

## RELATED LINKS

[Invoke-ServiceFabricFailoverTestScenario](./Invoke-ServiceFabricFailoverTestScenario.md)
