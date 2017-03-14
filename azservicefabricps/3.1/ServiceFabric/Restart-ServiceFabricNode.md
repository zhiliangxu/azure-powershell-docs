---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 31BD0C1D-F4E0-40B2-B902-06B660D633D9
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Restart-ServiceFabricNode.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Restart-ServiceFabricNode.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Restart-ServiceFabricNode

## SYNOPSIS
Restarts a Service Fabric node to simulate a cluster node failure.

## SYNTAX

### ByNodeName
```
Restart-ServiceFabricNode [-NodeName] <String> [[-NodeInstanceId] <BigInteger>]
 [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### PartitionIdReplicaPrimary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -PartitionId <Guid>
 -ServiceName <Uri> [-ReplicaKindPrimary] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### PartitionId
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -PartitionId <Guid>
 -ServiceName <Uri> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### PartitionIdReplicaRandomSecondary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -PartitionId <Guid>
 -ServiceName <Uri> [-ReplicaKindRandomSecondary] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### PartitionIdReplicaId
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -PartitionId <Guid>
 -ServiceName <Uri> -ReplicaOrInstanceId <Int64> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionUniformedIntReplicaRandomSecondary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindUniformInt64] -PartitionKey <String> [-ReplicaKindRandomSecondary] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionUniformedIntReplicaId
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindUniformInt64] -PartitionKey <String> -ReplicaOrInstanceId <Int64> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNameReplicaPrimary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-ReplicaKindPrimary] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNameReplicaRandomSecondary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-ReplicaKindRandomSecondary] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNameReplicaId
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 -ReplicaOrInstanceId <Int64> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceName
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionNamedReplicaId
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindNamed] -PartitionKey <String> -ReplicaOrInstanceId <Int64> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionNamed
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindNamed] -PartitionKey <String> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionUniformedInt
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindUniformInt64] -PartitionKey <String> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingletonReplicaRandomSecondary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindSingleton] [-ReplicaKindRandomSecondary] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionNamedReplicaRandomSecondary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindNamed] -PartitionKey <String> [-ReplicaKindRandomSecondary] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionSingleton
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindSingleton] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionSingletonReplicaPrimary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindSingleton] [-ReplicaKindPrimary] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionNamedReplicaPrimary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindNamed] -PartitionKey <String> [-ReplicaKindPrimary] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### ServiceNamePartitionUniformedIntReplicaPrimary
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindUniformInt64] -PartitionKey <String> [-ReplicaKindPrimary] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### ServiceNamePartitionSingletonReplicaId
```
Restart-ServiceFabricNode [-CommandCompletionMode <CompletionMode>] [-CreateFabricDump] -ServiceName <Uri>
 [-PartitionKindSingleton] -ReplicaOrInstanceId <Int64> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-ServiceFabricNode** cmdlet restarts a Service Fabric node by restarting the Fabric.exe process that hosts the node.
This cmdlet simulates Service Fabric node failures in the cluster, which tests the failover recovery paths of your service.

In addition to selecting a specific Service Fabric node, this cmdlet can accept a *ReplicaOrInstanceId* parameter to restart the primary replica.
This simplifies tests on the primary host node by not having to determine which Service Fabricnode is the primary node before restarting that node.

If you specify a non-zero value for the *NodeInstanceId* parameter, that ID is compared with the active node ID.
If the IDs do not match, the process is not restarted and an error occurs.
A stale message can cause this error.

If you specify the *CreateFabricDump* parameter, this cmdlet causes the Fabric.exe process to crash on the specified node during restart.
This crash creates a process dump for Fabric.exe.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Restart a node for a primary replica
```
PS C:\>Restart-ServiceFabricNode -ReplicaKindPrimary -PartitionKindNamed -PartitionKey "Partition3" -CommandCompletionMode Verify
```

This command restarts the specified node for a primary replica on the partition named Partition3.
Because the *CommandCompletionMode* parameter is specified with a value of Verify, the command waits for the target node to restart before it completes.

### Example 2: Restart a specified node
```
PS C:\>Restart-ServiceFabricNode -NodeName "Node01" -CommandCompletionMode DoNotVerify
```

This command restarts the node named Node01.
Because the *CommandCompletionMode* parameter is specified with a value of DoNotVerify, the command does not wait for the node to restart before it completes.

## PARAMETERS

### -CommandCompletionMode
Specifies whether the action waits for the restart to complete.

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

### -CreateFabricDump
Indicates that the Service Fabric node creates a process dump for Fabric.exe.

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

### -NodeInstanceId
Specifies a node instance ID.
Unless you specify 0, the node instance ID that you specify must match the currently running node.
The *NodeInstanceId* is also available through the query APIs.

```yaml
Type: BigInteger
Parameter Sets: ByNodeName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet restarts the node that you specify.

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
Specifies the ID of the partition of node to restart.

```yaml
Type: Guid
Parameter Sets: PartitionIdReplicaPrimary, PartitionId, PartitionIdReplicaRandomSecondary, PartitionIdReplicaId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKey
Specifies the key of the partition for the node to restart.

```yaml
Type: String
Parameter Sets: ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaId, ServiceNamePartitionNamedReplicaId, ServiceNamePartitionNamed, ServiceNamePartitionUniformedInt, ServiceNamePartitionNamedReplicaRandomSecondary, ServiceNamePartitionNamedReplicaPrimary, ServiceNamePartitionUniformedIntReplicaPrimary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKindNamed
Indicates that this cmdlet restarts a node on a named partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionNamedReplicaId, ServiceNamePartitionNamed, ServiceNamePartitionNamedReplicaRandomSecondary, ServiceNamePartitionNamedReplicaPrimary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionKindSingleton
Indicates that this cmdlet restarts a node on a singleton partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionSingletonReplicaRandomSecondary, ServiceNamePartitionSingleton, ServiceNamePartitionSingletonReplicaPrimary, ServiceNamePartitionSingletonReplicaId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionKindUniformInt64
Indicates that this cmdlet restarts a node on a UniformInt64 partition.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaId, ServiceNamePartitionUniformedInt, ServiceNamePartitionUniformedIntReplicaPrimary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaKindPrimary
Indicates that this cmdlet restarts the node for the primary replica.

```yaml
Type: SwitchParameter
Parameter Sets: PartitionIdReplicaPrimary, ServiceNameReplicaPrimary, ServiceNamePartitionSingletonReplicaPrimary, ServiceNamePartitionNamedReplicaPrimary, ServiceNamePartitionUniformedIntReplicaPrimary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaKindRandomSecondary
Indicates that this cmdlet restarts the node for a random secondary replica.

```yaml
Type: SwitchParameter
Parameter Sets: PartitionIdReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNameReplicaRandomSecondary, ServiceNamePartitionSingletonReplicaRandomSecondary, ServiceNamePartitionNamedReplicaRandomSecondary
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaOrInstanceId
Specifies a Service Fabric service replica or instance ID.

```yaml
Type: Int64
Parameter Sets: PartitionIdReplicaId, ServiceNamePartitionUniformedIntReplicaId, ServiceNameReplicaId, ServiceNamePartitionNamedReplicaId, ServiceNamePartitionSingletonReplicaId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the service to restart.

```yaml
Type: Uri
Parameter Sets: PartitionIdReplicaPrimary, PartitionId, PartitionIdReplicaRandomSecondary, PartitionIdReplicaId, ServiceNamePartitionUniformedIntReplicaRandomSecondary, ServiceNamePartitionUniformedIntReplicaId, ServiceNameReplicaPrimary, ServiceNameReplicaRandomSecondary, ServiceNameReplicaId, ServiceName, ServiceNamePartitionNamedReplicaId, ServiceNamePartitionNamed, ServiceNamePartitionUniformedInt, ServiceNamePartitionSingletonReplicaRandomSecondary, ServiceNamePartitionNamedReplicaRandomSecondary, ServiceNamePartitionSingleton, ServiceNamePartitionSingletonReplicaPrimary, ServiceNamePartitionNamedReplicaPrimary, ServiceNamePartitionUniformedIntReplicaPrimary, ServiceNamePartitionSingletonReplicaId
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

### System.Uri
Represents the name of a Service Fabric service.

### System.Guid
Represents the ID of a Service Fabric partition.

### string
Specifies the name of a Service Fabric node.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Testability.RestartNodeResult** object that represents the operation result.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Disable-ServiceFabricNode](./Disable-ServiceFabricNode.md)

[Enable-ServiceFabricNode](./Enable-ServiceFabricNode.md)

[Get-ServiceFabricNode](./Get-ServiceFabricNode.md)

[Start-ServiceFabricNode](./Start-ServiceFabricNode.md)

[Stop-ServiceFabricNode](./Stop-ServiceFabricNode.md)
