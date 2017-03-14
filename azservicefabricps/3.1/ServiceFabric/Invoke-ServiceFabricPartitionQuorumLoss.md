---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: C312AB4D-6C4F-404B-8335-A911EFFBD6E0
updated_at: 03/08/2017 13:03 PM
ms.date: 03/08/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricPartitionQuorumLoss.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricPartitionQuorumLoss.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/7b311e9dd04ae0a306bd8aacf179d0953aab7b57
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Invoke-ServiceFabricPartitionQuorumLoss

## SYNOPSIS
**DEPRECATED**. Please use the [Start-ServiceFabricPartitionQuorumLoss](./Start-ServiceFabricPartitionQuorumLoss.md).

## SYNTAX

### PartitionId
```
Invoke-ServiceFabricPartitionQuorumLoss -QuorumLossMode <QuorumLossMode> -QuorumLossDurationInSeconds <Int32>
 -PartitionId <Guid> -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionUniformedInt
```
Invoke-ServiceFabricPartitionQuorumLoss -QuorumLossMode <QuorumLossMode> -QuorumLossDurationInSeconds <Int32>
 -ServiceName <Uri> [-PartitionKindUniformInt64] -PartitionKey <String> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNameRandomPartition
```
Invoke-ServiceFabricPartitionQuorumLoss -QuorumLossMode <QuorumLossMode> -QuorumLossDurationInSeconds <Int32>
 -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingleton
```
Invoke-ServiceFabricPartitionQuorumLoss -QuorumLossMode <QuorumLossMode> -QuorumLossDurationInSeconds <Int32>
 -ServiceName <Uri> [-PartitionKindSingleton] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionNamed
```
Invoke-ServiceFabricPartitionQuorumLoss -QuorumLossMode <QuorumLossMode> -QuorumLossDurationInSeconds <Int32>
 -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-ServiceFabricPartitionQuorumLoss** cmdlet induces quorum loss in a Service Fabric partition for a specified amount of time.

## PARAMETERS

### -PartitionId
Specifies the ID of the partition on which to invoke the quorum loss.

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
Indicates that this cmdlet invokes a quorum loss on a named partition.

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
Indicates that this cmdlet invokes a quorum loss on a singleton partition.

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
Indicates that this cmdlet invokes a quorum loss for a UniformInt64 partitioned service.

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
Specifies the duration period, in seconds, for the quorum loss.

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
Specifies the quorum loss mode.

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

### System.Guid
Represents the ID of a Service Fabric partition.

### System.Uri
Represents the name of a Service Fabric service.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Testability.InvokeQuorumLossResult** object that represents the operation result.

## RELATED LINKS

[Invoke-ServiceFabricPartitionDataLoss](./Invoke-ServiceFabricPartitionDataLoss.md)
