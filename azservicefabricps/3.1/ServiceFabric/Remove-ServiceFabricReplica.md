---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 80D9F43B-395B-4295-8D5B-CE56BB0B6FA2
updated_at: 03/09/2017 05:03 AM
ms.date: 03/09/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricReplica.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricReplica.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/59bac2d879a84bc82847d8ab21abe35fdc370de4
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-ServiceFabricReplica

## SYNOPSIS
Removes a replica from a cluster to simulate a replica failure.

## SYNTAX

The following are the various ways of calling Remove-ServiceFabricReplica cmdlet.

### ByNodeName
```
Remove-ServiceFabricReplica [-ForceRemove] [-NodeName] <String> [-PartitionId] <Guid>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] -ReplicaOrInstanceId <Int64>
 [<CommonParameters>]
```

### PartitionId
```
Remove-ServiceFabricReplica [-ForceRemove] [-PartitionId] <Guid> -ServiceName <Uri>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### PartitionIdReplicaPrimary
```
Remove-ServiceFabricReplica [-ForceRemove] [-PartitionId] <Guid> -ServiceName <Uri>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [-ReplicaKindPrimary] [<CommonParameters>]
```

### PartitionIdReplicaRandomSecondary
```
Remove-ServiceFabricReplica [-ForceRemove] [-PartitionId] <Guid> -ServiceName <Uri>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [-ReplicaKindRandomSecondary]
 [<CommonParameters>]
```

### PartitionIdReplicaId
```
Remove-ServiceFabricReplica [-ForceRemove] [-PartitionId] <Guid> -ServiceName <Uri>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] -ReplicaOrInstanceId <Int64>
 [<CommonParameters>]
```

### ServiceNamePartitionSingletonReplicaId
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindSingleton]
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] -ReplicaOrInstanceId <Int64>
 [<CommonParameters>]
```

### ServiceNamePartitionNamedReplicaId
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] -ReplicaOrInstanceId <Int64>
 [<CommonParameters>]
```

### ServiceNamePartitionNamedReplicaPrimary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [-ReplicaKindPrimary] [<CommonParameters>]
```

### ServiceName
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-CommandCompletionMode <CompletionMode>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingleton
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindSingleton]
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionNamed
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionUniformedInt
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindUniformInt64]
 -PartitionKey <String> [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingletonReplicaRandomSecondary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindSingleton]
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [-ReplicaKindRandomSecondary]
 [<CommonParameters>]
```

### ServiceNamePartitionNamedReplicaRandomSecondary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindNamed] -PartitionKey <String>
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [-ReplicaKindRandomSecondary]
 [<CommonParameters>]
```

### ServiceNamePartitionUniformedIntReplicaRandomSecondary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindUniformInt64]
 -PartitionKey <String> [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>]
 [-ReplicaKindRandomSecondary] [<CommonParameters>]
```

### ServiceNamePartitionSingletonReplicaPrimary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindSingleton]
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [-ReplicaKindPrimary] [<CommonParameters>]
```

### ServiceNameReplicaId
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-CommandCompletionMode <CompletionMode>]
 [-TimeoutSec <Int32>] -ReplicaOrInstanceId <Int64> [<CommonParameters>]
```

### ServiceNamePartitionUniformedIntReplicaPrimary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindUniformInt64]
 -PartitionKey <String> [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [-ReplicaKindPrimary]
 [<CommonParameters>]
```

### ServiceNamePartitionUniformedIntReplicaId
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-PartitionKindUniformInt64]
 -PartitionKey <String> [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>]
 -ReplicaOrInstanceId <Int64> [<CommonParameters>]
```

### ServiceNameReplicaPrimary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-CommandCompletionMode <CompletionMode>]
 [-TimeoutSec <Int32>] [-ReplicaKindPrimary] [<CommonParameters>]
```

### ServiceNameReplicaRandomSecondary
```
Remove-ServiceFabricReplica [-ForceRemove] -ServiceName <Uri> [-CommandCompletionMode <CompletionMode>]
 [-TimeoutSec <Int32>] [-ReplicaKindRandomSecondary] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ServiceFabricReplica** cmdlet simulates a Service Fabric replica failure by removing a replica from a Service Fabric cluster.
The removal closes the replica, transitions the replica to the role None, and then removes all of the state information of the replica from the cluster.
This cmdlet tests the replica state removal path, and simulates the report fault permanent path through client APIs.

In order to specify the replica to be removed we can start either with the node name or the service name.

Then we need to specify the partition to which the replica belongs. We can specify the partition either by specifying the pair (naming scheme, partition key) or by specifying the partition ID. For more details on Microsoft Azure Service Fabric service partitioning, please refer to the [Partition Service Fabric reliable services](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-concepts-partitioning) article.  

Lastly, we may need to specify which replica of the partition we are referring to and that can be done either by specifying the replica role (primary or secondary replica) or by specifying the replica ID.

Note, sometimes the user may - instead of exactly specifying the replica - want to remove say one of the secondaries of a particular partition of a particular service; that is why, some of the forms of the Remove-ServiceFabricReplica cmdlet intentionally leaves ambiguity about which replica the user is referring to -- in these cases, the cmdlet makes random choices for the user. For example, if the user only provides the service name to the cmdlet, the Remove-ServiceFabricReplica cmdlet will assume that the user wants to remove any one of the replicas from any one of the partitions belonging to the service; so it will choose one of the partitions of the service at random and will choose one of the replicas (could be primary or secondary) of the chosen partition at random and will remove that chosen replica.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.


## EXAMPLES

### Example 1: Remove a specific replica
```
PS C:\>Remove-ServiceFabricReplica -NodeName "Node07" -PartitionId 869dd2e9-fdda-42a5-ad96-4b71c795dfd3 -ReplicaOrInstanceId 12345098480948
```

This command removes a replica that belongs to the specified partition that is deployed on the specified node.

### Example 2: Remove a primary replica
```
PS C:\>Remove-ServiceFabricReplica -ReplicaKindPrimary -PartitionKindNamed -PartitionKey "Partition1" -ServiceName fabric:/App/Service
```
This command removes the primary replica that belongs to a specified named partition.

### Example 3: Remove some replica of a specific partition
```
PS C:> Remove-ServiceFabricReplica -ServiceName fabric:/Application37/Stateful1 -PartitionId  2fb4f54b-
bd1e-4b48-972c-ef25b071d607


SelectedReplica : ReplicaOrInstanceId = 131334070761552043, SelectedPartition = Service Name:
                  fabric:/Application37/Stateful1, Partition Id: 2fb4f54b-bd1e-4b48-972c-ef25b071d607
```

This command removes a randomly chosen replica from the partition with ID 2fb4f54b-bd1e-4b48-972c-ef25b071d607 of the service fabric:/Application37/Stateful1. The output also shows that the ID of the randomly chosen replica is 131334070761552043.


## PARAMETERS

### -CommandCompletionMode
Specifies whether the action waits for the remove operation to complete.

```yaml
Type: CompletionMode
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, DoNotVerify, Verify

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceRemove
Indicates that this cmdlet forces removal of the replica.

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

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet removes a replica deployed on the node that you specify.

```yaml
Type: String
Parameter Sets: ByNodeName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionId
Specifies the ID of the partition from which to remove the replica.

```yaml
Type: Guid
Parameter Sets: ByNodeName, PartitionId, PartitionIdReplicaPrimary, PartitionIdReplicaRandomSecondary, PartitionIdReplicaId
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKey
Specifies the partition key.

```yaml
Type: String
Parameter Sets: ServiceNamePartitionNamedReplicaId, ServiceNamePartitionNamedReplicaPrimary, ServiceNamePartitionNamed, ServiceNamePartitionUniformedInt, ServiceNamePartitionNamedReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaPrimary, ServiceNamePartitionUniformedIntReplicaId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKindNamed
Indicates that this cmdlet removes a replica on a named partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionNamedReplicaId, ServiceNamePartitionNamedReplicaPrimary, ServiceNamePartitionNamed, ServiceNamePartitionNamedReplicaRandomSecondary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKindSingleton
Indicates that this cmdlet removes a replica on a singleton partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionSingletonReplicaId, ServiceNamePartitionSingleton, ServiceNamePartitionSingletonReplicaRandomSecondary, ServiceNamePartitionSingletonReplicaPrimary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKindUniformInt64
Indicates that this cmdlet removes a replica on a UniformInt64 partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionUniformedInt, ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaPrimary, ServiceNamePartitionUniformedIntReplicaId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaKindPrimary
Indicates that this cmdlet removes the replica for the primary replica.

```yaml
Type: SwitchParameter
Parameter Sets: PartitionIdReplicaPrimary, ServiceNamePartitionNamedReplicaPrimary, ServiceNamePartitionSingletonReplicaPrimary, ServiceNamePartitionUniformedIntReplicaPrimary, ServiceNameReplicaPrimary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaKindRandomSecondary
Indicates that this cmdlet removes a replica for a random secondary replica.

```yaml
Type: SwitchParameter
Parameter Sets: PartitionIdReplicaRandomSecondary, ServiceNamePartitionSingletonReplicaRandomSecondary, ServiceNamePartitionNamedReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNameReplicaRandomSecondary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaOrInstanceId
Specifies a Service Fabric service replica or instance ID.

```yaml
Type: Int64
Parameter Sets: ByNodeName, PartitionIdReplicaId, ServiceNamePartitionSingletonReplicaId, ServiceNamePartitionNamedReplicaId, ServiceNameReplicaId, ServiceNamePartitionUniformedIntReplicaId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the service that this cmdlet removes.

```yaml
Type: Uri
Parameter Sets: PartitionId, PartitionIdReplicaPrimary, PartitionIdReplicaRandomSecondary, PartitionIdReplicaId, ServiceNamePartitionSingletonReplicaId, ServiceNamePartitionNamedReplicaId, ServiceNamePartitionNamedReplicaPrimary, ServiceName, ServiceNamePartitionSingleton, ServiceNamePartitionNamed, ServiceNamePartitionUniformedInt, ServiceNamePartitionSingletonReplicaRandomSecondary, ServiceNamePartitionNamedReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNamePartitionSingletonReplicaPrimary, ServiceNameReplicaId, ServiceNamePartitionUniformedIntReplicaPrimary, ServiceNamePartitionUniformedIntReplicaId, ServiceNameReplicaPrimary, ServiceNameReplicaRandomSecondary
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
This cmdlet accepts the ID of a Service Fabric partition.

### String
This cmdlet accepts the name of a Service Fabric node.

### System.Uri
This cmdlet accepts the name of a Service Fabric service.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Result.RemoveReplicaResult** object that represents the operation result.

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricReplica](./Get-ServiceFabricReplica.md)
