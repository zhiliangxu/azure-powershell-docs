---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 0A01F959-D065-4EEC-BA1C-28B623F49416
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricReplica.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricReplica.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricReplica

## SYNOPSIS
Gets Service Fabric replicas.

## SYNTAX

```
Get-ServiceFabricReplica [-PartitionId] <Guid> [[-ReplicaOrInstanceId] <Int64>]
 [-ReplicaStatusFilter <ServiceReplicaStatusFilter>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricReplica** cmdlet gets Service Fabric replicas of a partition.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the replica for a partition
```
PS C:\>$CalculatorPartition01 = Get-ServiceFabricPartition -ServiceName fabric:/myapp/calculator/svc1
PS C:\> Get-ServiceFabricReplica -PartitionId $CalculatorPartition01.PartitionId
```

The first command uses the [Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md) cmdlet to get the partition for the specified service, and then stores it in the $CalculatorPartition01.

The second command gets the Service Fabric replica by using the **PartitionId** property of the partition stored in $CalculatorPartition01.

### Example 2: Get the partitioned replicas for a system service
```
PS C:\>Get-ServiceFabricPartition -ServiceName fabric:/System/FailoverManagerService | Get-ServiceFabricReplica
```

This command gets the list of partitions for the Failover Manager system service.

## PARAMETERS

### -PartitionId
Specifies the ID of a Service Fabric partition.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaOrInstanceId
Specifies a Service Fabric service replica or instance ID.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaStatusFilter
Specifies the replica status filter as a **ServiceReplicaStatusFilter** object.

```yaml
Type: ServiceReplicaStatusFilter
Parameter Sets: (All)
Aliases:
Accepted values: Default, InBuild, Standby, Ready, Down, Dropped, All

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid, Int64
This cmdlet accepts the ID of a Service Fabric partition, or a replica or instance ID.

## OUTPUTS

### System.Object
This cmdlet returns a list of **System.Fabric.Query.Replica** objects.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md)
