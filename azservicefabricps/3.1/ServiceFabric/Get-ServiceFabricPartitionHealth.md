---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 329D70B6-FABD-4BB4-AE54-2E177E8246B9
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionHealth.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionHealth.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricPartitionHealth

## SYNOPSIS
Gets the health of a Service Fabric partition.

## SYNTAX

```
Get-ServiceFabricPartitionHealth [-PartitionId] <Guid> [-ConsiderWarningAsError <Boolean>]
 [-MaxPercentUnhealthyReplicasPerPartition <Byte>] [-EventsHealthStateFilter <Int64>]
 [-EventsFilter <HealthStateFilter>] [-ReplicasHealthStateFilter <Int64>] [-ReplicasFilter <HealthStateFilter>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricPartitionHealth** cmdlet gets the health of a Service Fabric partition.
If you specify a partition that does not exist in the health store, this cmdlet returns an error.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the health events for of a service partition
```
PS C:\>$ToDoPartition01 = Get-ServiceFabricPartition -ServiceName fabric:/myapp/persistenttodolist/svc1PS
C:\> Get-ServiceFabricPartitionHealth -PartitionId $ToDoPartition01.PartitionId
```

The first command uses the [Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md) cmdlet to get the singleton service partition object for the specified service, and then stores the object in the $ToDoPartition01 variable.

The second command gets the health of the partition by using the **PartitionId** property of the object stored in $ToDoPartition01.

### Example 2: Query the health of a service partition using custom health policy and return filters
```
PS C:\>Get-ServiceFabricPartition -ServiceName fabric:/myapp/persistenttodolist/svc1PS | Get-ServiceFabricPartitionHealth -ConsiderWarningAsError $True -EventsFilter Error
```

This command queries the health of the partitions of the specified service.
It uses custom health policy and filter to return only Error events.

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
Specifies the filter for the collection of **HealthEvent**s reported on the partition based on health state.
The value can be obtained from members or bitwise operations on members of **HealthStateFilter**.
Only events that match the filter are returned.
All events are used to evaluate the partition's aggregated health state.
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

### -MaxPercentUnhealthyReplicasPerPartition
Specifies the maximum tolerated percentage of unhealthy replicas in a partition.
If there are more replicas with a health state error than tolerated, the health state of the partition is error.

```yaml
Type: Byte
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

### -ReplicasFilter
Specifies the filter for **ReplicaHealthState** children based on health state.
The value can be obtained from members or bitwise operations on members of **HealthStateFilter**.
Only children that match the filter are returned.
All children are used to evaluate the entity aggregated health state.
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

### -ReplicasHealthStateFilter
This parameter has been deprecated.
Specify the *ReplicasFilter* parameter instead.

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

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Health.PartitionHealth** object that represents the health of a Service Fabric partition.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md)
