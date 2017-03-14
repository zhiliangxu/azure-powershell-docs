---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 03B1C1AE-DF27-4EA0-8423-7224A9174AA3
updated_at: 11/03/2016 08:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricReplicaHealth.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricReplicaHealth.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/1ee1eb862e0b78a20a656aad5e958efd0f11f85c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricReplicaHealth

## SYNOPSIS
Gets the health of a Service Fabric replica.

## SYNTAX

```
Get-ServiceFabricReplicaHealth [-PartitionId] <Guid> [-ReplicaOrInstanceId] <Int64>
 [-ConsiderWarningAsError <Boolean>] [-EventsHealthStateFilter <Int64>] [-EventsFilter <HealthStateFilter>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricReplicaHealth** cmdlet gets the health of a Service Fabric replica.
If the replica that you specify does not exist in the health store, this cmdlet returns an exception.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Query the health of a service replica
```
PS C:\>$ToDoPartition01 = Get-ServiceFabricPartition -ServiceName fabric:/myapp/persistenttodolist/svc1PS
C:\> $ToDoPartition01ReplicaList = Get-ServiceFabricReplica -PartitionId $ToDoPartition01.PartitionId
C:\> Get-ServiceFabricReplicaHealth -PartitionId $ToDoPartition01.PartitionId -ReplicaOrInstanceId $ToDoPartition01ReplicaList[0].Id
```

The first command uses the [Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md) cmdlet to get a Service Fabric service partition object, and then stores it in the $ToDoPartition01 variable.

The second command gets the list of replicas in the partition, and then stores it in the $ToDoPartition01ReplicaList variable.

The third command gets the health of a service partition replica by using the **PartitionID** property of the partition object stored in $ToDoPartition01 and the ID of the first replica in $ToDoPartition01ReplicaList.

### Example 2: Query the health of a service replica using custom health policy and return filters
```
PS C:\>$replicaList = Get-ServiceFabricPartition -ServiceName fabric:/myapp/persistenttodolist/svc1PS | Get-ServiceFabricReplica
C:\> Get-ServiceFabricReplicaHealth -PartitionId $replicaList[0].PartitionId -ReplicaOrInstanceId $replicaList[0].ReplicaId -ConsiderWarningAsError $True -EventsFilter Error
```

This example queries the health of the service replica.
It specifies values for health policy.
It uses filters to return only Error events.

### Example 3: Get the health of all replicas of all partitions of all services in an application
```
PS C:\>Get-ServiceFabricApplication -ApplicationName fabric:/MyApplication | Get-ServiceFabricService | Get-ServiceFabricPartition | Get-ServiceFabricReplica | Get-ServiceFabricReplicaHealth
```

This example gets the health of all service replicas in the specified application.

## PARAMETERS

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

### -EventsFilter
Specifies the filter for the collection of **HealthEvent** reported on the entity based on health state.
The value can be obtained from members or bitwise operations on members of **HealthStateFilter**.
Only events that match the filter are returned.
All events are used to evaluate the aggregated health state.
If not specified, all entries are returned.

```yaml
Type: HealthStateFilter
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Ok, Warning, Error, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventsHealthStateFilter
This parameter has been deprecated.
Specify the *EventsFilter* parameter instead.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Specifies a Service Fabric stateful service replica or stateless service instance ID.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### System.Guid, Int64
This cmdlet accepts the ID or a Service Fabric partition, or a replica or instance ID.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Health** object that represents the health of a Service Fabric replica.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md)
