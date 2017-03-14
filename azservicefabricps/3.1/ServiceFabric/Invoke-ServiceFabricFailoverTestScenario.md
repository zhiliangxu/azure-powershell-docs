---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: BEA22E4F-87EE-48AC-9406-E8A05BB8A740
updated_at: 11/03/2016 08:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricFailoverTestScenario.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricFailoverTestScenario.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/1ee1eb862e0b78a20a656aad5e958efd0f11f85c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Invoke-ServiceFabricFailoverTestScenario

## SYNOPSIS
Invokes a test scenario to induce faults in a Service Fabric partition.

## SYNTAX

### PartitionId
```
Invoke-ServiceFabricFailoverTestScenario -MaxServiceStabilizationTimeoutSec <UInt32> -TimeToRunMinute <UInt32>
 [-WaitTimeBetweenFaultsSec <Int32>] -PartitionId <Guid> -ServiceName <Uri> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionUniformedInt
```
Invoke-ServiceFabricFailoverTestScenario -MaxServiceStabilizationTimeoutSec <UInt32> -TimeToRunMinute <UInt32>
 [-WaitTimeBetweenFaultsSec <Int32>] -ServiceName <Uri> [-PartitionKindUniformInt64] -PartitionKey <String>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNameRandomPartition
```
Invoke-ServiceFabricFailoverTestScenario -MaxServiceStabilizationTimeoutSec <UInt32> -TimeToRunMinute <UInt32>
 [-WaitTimeBetweenFaultsSec <Int32>] -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingleton
```
Invoke-ServiceFabricFailoverTestScenario -MaxServiceStabilizationTimeoutSec <UInt32> -TimeToRunMinute <UInt32>
 [-WaitTimeBetweenFaultsSec <Int32>] -ServiceName <Uri> [-PartitionKindSingleton] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionNamed
```
Invoke-ServiceFabricFailoverTestScenario -MaxServiceStabilizationTimeoutSec <UInt32> -TimeToRunMinute <UInt32>
 [-WaitTimeBetweenFaultsSec <Int32>] -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-ServiceFabricFailoverTestScenario** cmdlet starts a test scenario to induce faults in a Service Fabric partition.
The test puts the partition through specific failover scenarios to ensure those paths are exercised.
If you run a workload against a Service Fabric service while the cmdlet runs its tests, you increase the chance of discovering bugs in the service.

The faults induced for the primary, secondary, and stateless instances are:

- RestartReplica (only persisted)
- RemoveReplica
- ResartDeployedCodePackage
- MovePrimary (only stateful)
- MoveSecondary (only stateful)
- RestartPartition (no data loss)

Before using this cmdlet, connect to the Service Fabric cluster.

## EXAMPLES

### Example 1: Run a failover test
```
PS C:\>$TimeToRun = 60
PS C:\> $MaxStabilizationTimeSecs = 180
PS C:\> $WaitTimeBetweenFaultsSec = 10
PS C:\> $ServiceName = "fabric:/SampleApp/SampleService"
PS C:\> Invoke-ServiceFabricFailoverTestScenario -TimeToRunMinute $TimeToRun -MaxServiceStabilizationTimeoutSec $MaxStabilizationTimeSecs -WaitTimeBetweenFaultsSec $WaitTimeBetweenFaultsSec -ServiceName $ServiceName -PartitionKindSingleton
```

## PARAMETERS

### -MaxServiceStabilizationTimeoutSec
Specifies the maximum time-out period, in seconds, for the service to stabilize before failing the test.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionId
Specifies the ID of the partition to test.

```yaml
Type: Guid
Parameter Sets: PartitionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKey
Specifies the key of the partition on which to invoke the test.

```yaml
Type: String
Parameter Sets: ServiceNamePartitionUniformedInt, ServiceNamePartitionNamed
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKindNamed
Indicates that this cmdlet tests a named partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionNamed
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionKindSingleton
Indicates that this cmdlet tests a singleton partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionSingleton
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionKindUniformInt64
Indicates that this cmdlet tests a UniformInt64 partitioned service.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionUniformedInt
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the service to test.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeToRunMinute
Specifies the total time, in minutes, for the scenario to run.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
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

### -WaitTimeBetweenFaultsSec
Specifies the maximum wait time, in seconds, between consecutive faults.
The larger the value the lower the concurrency.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid
Represents the ID of a Service Fabric partition.

### System.Uri
Represents the name of a Service Fabric service.

## OUTPUTS

### System.Object
This cmdlet returns a **String** object that represents the final status of the test run.

## NOTES

## RELATED LINKS
