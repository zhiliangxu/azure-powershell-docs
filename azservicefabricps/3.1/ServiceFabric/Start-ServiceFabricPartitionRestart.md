---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 2E71980D-7493-4C14-BA4A-1AB48398594A
updated_at: 03/07/2017 08:03 AM
ms.date: 03/07/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricPartitionRestart.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricPartitionRestart.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/d66df4faefd1944c1099d7424481053e0f5f3a72
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Start-ServiceFabricPartitionRestart

## SYNOPSIS
Initiates the restart of a stateful service partition.

## SYNTAX

### PartitionId
```
Start-ServiceFabricPartitionRestart -OperationId <Guid> -RestartPartitionMode <RestartPartitionMode>
 -PartitionId <Guid> -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionUniformedInt
```
Start-ServiceFabricPartitionRestart -OperationId <Guid> -RestartPartitionMode <RestartPartitionMode>
 -ServiceName <Uri> [-PartitionKindUniformInt64] -PartitionKey <String> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNameRandomPartition
```
Start-ServiceFabricPartitionRestart -OperationId <Guid> -RestartPartitionMode <RestartPartitionMode>
 -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingleton
```
Start-ServiceFabricPartitionRestart -OperationId <Guid> -RestartPartitionMode <RestartPartitionMode>
 -ServiceName <Uri> [-PartitionKindSingleton] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionNamed
```
Start-ServiceFabricPartitionRestart -OperationId <Guid> -RestartPartitionMode <RestartPartitionMode>
 -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-ServiceFabricPartitionRestart** cmdlet initiates the restart of a stateful service partition in Azure Service Fabric.
To run this cmdlet, **FaultAnalysisService** must be enabled.

Run this cmdlet to restart only partitions for stateful services.
Do not use this cmdlet to restart partitions for system services.

You can check the progress of the operation by using the [Get-ServiceFabricPartitionRestartProgress](./Get-ServiceFabricPartitionRestartProgress.md) cmdlet.

## EXAMPLES

### Example 1: Restart all replicas of a service by partition ID
```
PS C:\>Start-ServiceFabricPartitionRestart -OperationId 53ba886b-79be-46ee-bf7e-d79db64eb003 -RestartPartitionMode AllReplicasOrInstances -PartitionId 20a726d0-3112-4c5a-a22c-2e4b8ee85280 -ServiceName "fabric:/ContosoApp/ContosoService"
```

This command restarts all replicas of the service named fabric:/ContosoApp/ContosoService in the partition that has the ID 20a726d0-3112-4c5a-a22c-2e4b8ee85280.
Specify a unique GUID for the *OperationId* parameter.
You can use this ID to check the progress of the restart operation.

### Example 2: Restart all replicas of a service by partition key
```
PS C:\>Start-ServiceFabricPartitionRestart -OperationId ebd322c2-b1d3-46a7-b254-3cc42e6ca2d1 -RestartPartitionMode AllReplicasOrInstances -ServiceName "fabric:/ContosoApp/ContosoService" -PartitionKindUniformInt64 -PartitionKey 2000
```

This command restarts all replicas of the service named fabric:/ContosoApp/ContosoService in the partition that has the partition key 2000.
Specify a unique GUID for the *OperationId* parameter.

## PARAMETERS

### -OperationId
Specifies a unique identifier for this operation.
Specify a unique value.
You can check the progress of the operation by using this ID and the **Get-ServiceFabricPartitionRestartProgress** cmdlet.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionId
Specifies the ID of the Service Fabric partition that this cmdlet restarts.

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
Specifies the key of the Service Fabric partition that this cmdlet restarts.

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
Indicates that the Service Fabric partition that this cmdlet restarts is a Named partition.

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
Indicates that the Service Fabric partition that this cmdlet restarts is a singleton partition.

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
Indicates that the Service Fabric partition that this cmdlet restarts is a UniformInt64 partition.

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

### -RestartPartitionMode
Specifies the mode for the partition restart operation.
The acceptable values for this parameter are:

- AllReplicasOrInstances.
Restart all replicas in the target partition.
- OnlyActiveSecondaries.
Restart only the secondaries in the target partition.

```yaml
Type: RestartPartitionMode
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, AllReplicasOrInstances, OnlyActiveSecondaries

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric service.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ServiceFabricPartitionRestartProgress](./Get-ServiceFabricPartitionRestartProgress.md)
