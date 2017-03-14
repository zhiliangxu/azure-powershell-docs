---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 199F858A-4F1C-44C4-9723-D651FE5FAF44
updated_at: 03/09/2017 05:03 AM
ms.date: 03/09/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricPartitionQuorumLoss.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricPartitionQuorumLoss.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/59bac2d879a84bc82847d8ab21abe35fdc370de4
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Start-ServiceFabricPartitionQuorumLoss

## SYNOPSIS
Initiates a fault to put a partition into quorum loss.

## SYNTAX
The various ways to specify or to choose the partition to invoke quorum loss on are as follows:

### PartitionId
```
Start-ServiceFabricPartitionQuorumLoss -OperationId <Guid> -QuorumLossMode <QuorumLossMode>
 -QuorumLossDurationInSeconds <Int32> -PartitionId <Guid> -ServiceName <Uri> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionUniformedInt
```
Start-ServiceFabricPartitionQuorumLoss -OperationId <Guid> -QuorumLossMode <QuorumLossMode>
 -QuorumLossDurationInSeconds <Int32> -ServiceName <Uri> [-PartitionKindUniformInt64] -PartitionKey <String>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNameRandomPartition
```
Start-ServiceFabricPartitionQuorumLoss -OperationId <Guid> -QuorumLossMode <QuorumLossMode>
 -QuorumLossDurationInSeconds <Int32> -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingleton
```
Start-ServiceFabricPartitionQuorumLoss -OperationId <Guid> -QuorumLossMode <QuorumLossMode>
 -QuorumLossDurationInSeconds <Int32> -ServiceName <Uri> [-PartitionKindSingleton] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionNamed
```
Start-ServiceFabricPartitionQuorumLoss -OperationId <Guid> -QuorumLossMode <QuorumLossMode>
 -QuorumLossDurationInSeconds <Int32> -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-ServiceFabricPartitionQuorumLoss** cmdlet initiates a fault to put a stateful service partition into quorum loss in Azure Service Fabric.

> [!WARNING]
> Do not use this cmdlet to perform a quorum loss fault operation on system services.
> Run this cmdlet to perform a quorum loss fault operation only for partitions for stateful services.
>

You can check the progress of the fault operation by using the [Get-ServiceFabricPartitionQuorumLossProgress](./Get-ServiceFabricPartitionQuorumLossProgress) cmdlet.

## EXAMPLES

### Example 1: Start a quorum loss fault operation for a service by partition ID
```
PS C:\>Start-ServiceFabricPartitionQuorumLoss -OperationId aeaceca9-320d-4f7b-84e8-3cc13c29a974 -QuorumLossMode QuorumReplicas -QuorumLossDurationInSeconds 10 -PartitionId 20a726d0-3112-4c5a-a22c-2e4b8ee85280 -ServiceName "fabric:/ContosoApp/ContosoService"
```

This command starts a partition quorum loss fault operation on the service named fabric:/ContosoApp/ContosoService in the partition that has the ID 20a726d0-3112-4c5a-a22c-2e4b8ee85280.
The *QuorumLossMode* parameter has a value of QuorumReplicas, which means that this cmdlet faults a quorum of replicas.
Specify a unique GUID for the *OperationId* parameter.
You can use this ID to check the progress of the quorum loss fault operation.

## PARAMETERS

### -OperationId
Specifies a unique identifier for this operation.
Specify a unique value.
You can check the progress of the operation by passing this ID into **Get-ServiceFabricPartitionQuorumLossProgress**.

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
Specifies the ID of the Service Fabric partition that this cmdlet puts into quorum loss.

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
Specifies the key of the Service Fabric partition that this cmdlet puts into quorum loss.

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
Indicates that the Service Fabric partition that this cmdlet puts into quorum loss is a Named partition.

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
Indicates that the Service Fabric partition that this cmdlet puts into quorum loss is a singleton partition.

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
Indicates that the Service Fabric partition that this cmdlet puts into quorum loss is a UniformInt64 partition.

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

### -QuorumLossDurationInSeconds
Specifies the duration, in seconds, of the quorum loss.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuorumLossMode
Specifies the mode of quorum loss that this cmdlet performs.
The acceptable values for this parameter are:

- FullQuorumLoss.
Down all replicas for the target partition.
- PartialQuorumLoss.
Down a quorum of replicas for the target partition.

```yaml
Type: QuorumLossMode
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, QuorumReplicas, AllReplicas

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

## RELATED LINKS

[Get-ServiceFabricPartitionQuorumLossProgress](./Get-ServiceFabricPartitionQuorumLossProgress.md)

[Invoke-ServiceFabricPartitionQuorumLoss](./Invoke-ServiceFabricPartitionQuorumLoss.md)
