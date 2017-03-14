---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 22D597E5-47A6-483C-88C6-DDAC072424DE
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Move-ServiceFabricPrimaryReplica.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Move-ServiceFabricPrimaryReplica.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Move-ServiceFabricPrimaryReplica

## SYNOPSIS
Moves the Service Fabric primary replica of a stateful service partition.

## SYNTAX

### PartitionId
```
Move-ServiceFabricPrimaryReplica [-NodeName <String>] [-IgnoreConstraints <Boolean>] -PartitionId <Guid>
 -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionUniformedInt
```
Move-ServiceFabricPrimaryReplica [-NodeName <String>] [-IgnoreConstraints <Boolean>] -ServiceName <Uri>
 [-PartitionKindUniformInt64] -PartitionKey <String> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNameRandomPartition
```
Move-ServiceFabricPrimaryReplica [-NodeName <String>] [-IgnoreConstraints <Boolean>] -ServiceName <Uri>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingleton
```
Move-ServiceFabricPrimaryReplica [-NodeName <String>] [-IgnoreConstraints <Boolean>] -ServiceName <Uri>
 [-PartitionKindSingleton] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionNamed
```
Move-ServiceFabricPrimaryReplica [-NodeName <String>] [-IgnoreConstraints <Boolean>] -ServiceName <Uri>
 [-PartitionKindNamed] -PartitionKey <String> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-ServiceFabricPrimaryReplica** cmdlet moves the Service Fabric primary replica of a stateful service partition from the current primary node to a specified node.
You can also perform this operation on system services.
You cannot use this cmdlet for stateless services.

The **Move-ServiceFabricPrimaryReplica** cmdlet moves the primary replica to a new Service Fabric node location after the command is accepted.
However, the load balancer may move the primary replica again based on load balancer constraints or on the load balancer balancing algorithm.

To use this cmdlet, you must be a member of the Administrators group.

Before using this cmdlet, connect to the Service Fabric cluster.

## EXAMPLES

### Example 1: Move the primary replica of a stateful service partition to a specified node
```
PS C:\>Move-ServiceFabricPrimaryReplica -PartitionId 93838f53-f1d9-4b99-8492-b802ee807d03 -NodeName "N0050" -ServiceName fabric:/SampleApp/SampleService
```

This command moves the primary replica of the specified stateful service partition to the node named N0050.

### Example 2: Move the primary replica of a stateful service partition to a random node
```
PS C:\>Move-ServiceFabricPrimaryReplica -ServiceName fabric:/SampleApp/SampleService -PartitionId 93838f53-f1d9-4b99-8492-b802ee807d03
```

This command moves the primary replica of the specified stateful service partition to a random node because the *NodeName* parameter is not specified.

### Example 3: Move the primary replica of a stateful service partition to a random node
```
PS C:\>Move-ServiceFabricPrimaryReplica -ServiceName fabric:/SampleApp1/PersistServ
```

This command moves the primary replica of the specified stateful service partition to a random node because the *NodeName* parameter is not specified.
A random partition for the specified service is selected.

## PARAMETERS

### -IgnoreConstraints
Indicates whether the cmdlet ignores constraints.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet moves the primary replica to the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionId
Specifies the ID of the partition to move.

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
Specifies the key of the partition to move.

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
Indicates that this cmdlet moves a named partition.

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
Indicates that this cmdlet moves a singleton partition.

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
Indicates that this cmdlet moves a UniformInt64 partitioned service.

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
Specifies the service name of the replica to move.

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

### string
Specifies the name of a Service Fabric node.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Testability.MovePrimaryResult** object that represents the operation result.

## NOTES

## RELATED LINKS

[Move-ServiceFabricSecondaryReplica](./Move-ServiceFabricSecondaryReplica.md)
