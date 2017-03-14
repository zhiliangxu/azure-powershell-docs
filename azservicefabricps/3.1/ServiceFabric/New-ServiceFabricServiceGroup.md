---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 8A21CCA5-D38A-4DF7-98F0-21F18BCC4842
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricServiceGroup.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricServiceGroup.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-ServiceFabricServiceGroup

## SYNOPSIS
Creates a Service Fabric service group.

## SYNTAX

### Stateless Singleton Non-Adhoc (Default)
```
New-ServiceFabricServiceGroup [-Stateless] [-PartitionSchemeSingleton] [-ApplicationName] <Uri>
 [-ServiceName] <Uri> [-ServiceTypeName] <String> -InstanceCount <Int32> [-PlacementConstraint <String>]
 [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateful UniformInt64 Adhoc
```
New-ServiceFabricServiceGroup [-Stateful] [-PartitionSchemeUniformInt64] [-Adhoc] [-ServiceName] <Uri>
 [-ServiceTypeName] <String> -PartitionCount <Int32> -LowKey <Int64> -HighKey <Int64> [-HasPersistedState]
 -TargetReplicaSetSize <Int32> -MinReplicaSetSize <Int32> [-ReplicaRestartWaitDuration <TimeSpan>]
 [-QuorumLossWaitDuration <TimeSpan>] [-PlacementConstraint <String>] [-Metric <String[]>]
 [-Correlation <String[]>] [-PlacementPolicy <String[]>] -ServiceGroupMemberDescription <Hashtable[]>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateful Singleton Non-Adhoc
```
New-ServiceFabricServiceGroup [-Stateful] [-PartitionSchemeSingleton] [-ApplicationName] <Uri>
 [-ServiceName] <Uri> [-ServiceTypeName] <String> [-HasPersistedState] -TargetReplicaSetSize <Int32>
 -MinReplicaSetSize <Int32> [-ReplicaRestartWaitDuration <TimeSpan>] [-QuorumLossWaitDuration <TimeSpan>]
 [-PlacementConstraint <String>] [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateful UniformInt64 Non-Adhoc
```
New-ServiceFabricServiceGroup [-Stateful] [-PartitionSchemeUniformInt64] [-ApplicationName] <Uri>
 [-ServiceName] <Uri> [-ServiceTypeName] <String> -PartitionCount <Int32> -LowKey <Int64> -HighKey <Int64>
 [-HasPersistedState] -TargetReplicaSetSize <Int32> -MinReplicaSetSize <Int32>
 [-ReplicaRestartWaitDuration <TimeSpan>] [-QuorumLossWaitDuration <TimeSpan>] [-PlacementConstraint <String>]
 [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateful Named Non-Adhoc
```
New-ServiceFabricServiceGroup [-Stateful] [-PartitionSchemeNamed] [-ApplicationName] <Uri> [-ServiceName] <Uri>
 [-ServiceTypeName] <String> -PartitionNames <String[]> [-HasPersistedState] -TargetReplicaSetSize <Int32>
 -MinReplicaSetSize <Int32> [-ReplicaRestartWaitDuration <TimeSpan>] [-QuorumLossWaitDuration <TimeSpan>]
 [-PlacementConstraint <String>] [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateful Singleton Adhoc
```
New-ServiceFabricServiceGroup [-Stateful] [-PartitionSchemeSingleton] [-Adhoc] [-ServiceName] <Uri>
 [-ServiceTypeName] <String> [-HasPersistedState] -TargetReplicaSetSize <Int32> -MinReplicaSetSize <Int32>
 [-ReplicaRestartWaitDuration <TimeSpan>] [-QuorumLossWaitDuration <TimeSpan>] [-PlacementConstraint <String>]
 [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateful Named Adhoc
```
New-ServiceFabricServiceGroup [-Stateful] [-PartitionSchemeNamed] [-Adhoc] [-ServiceName] <Uri>
 [-ServiceTypeName] <String> -PartitionNames <String[]> [-HasPersistedState] -TargetReplicaSetSize <Int32>
 -MinReplicaSetSize <Int32> [-ReplicaRestartWaitDuration <TimeSpan>] [-QuorumLossWaitDuration <TimeSpan>]
 [-PlacementConstraint <String>] [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateless Named Adhoc
```
New-ServiceFabricServiceGroup [-Stateless] [-PartitionSchemeNamed] [-Adhoc] [-ServiceName] <Uri>
 [-ServiceTypeName] <String> -PartitionNames <String[]> -InstanceCount <Int32> [-PlacementConstraint <String>]
 [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateless UniformInt64 Non-Adhoc
```
New-ServiceFabricServiceGroup [-Stateless] [-PartitionSchemeUniformInt64] [-ApplicationName] <Uri>
 [-ServiceName] <Uri> [-ServiceTypeName] <String> -PartitionCount <Int32> -LowKey <Int64> -HighKey <Int64>
 -InstanceCount <Int32> [-PlacementConstraint <String>] [-Metric <String[]>] [-Correlation <String[]>]
 [-PlacementPolicy <String[]>] -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### Stateless Named Non-Adhoc
```
New-ServiceFabricServiceGroup [-Stateless] [-PartitionSchemeNamed] [-ApplicationName] <Uri>
 [-ServiceName] <Uri> [-ServiceTypeName] <String> -PartitionNames <String[]> -InstanceCount <Int32>
 [-PlacementConstraint <String>] [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateless Singleton Adhoc
```
New-ServiceFabricServiceGroup [-Stateless] [-PartitionSchemeSingleton] [-Adhoc] [-ServiceName] <Uri>
 [-ServiceTypeName] <String> -InstanceCount <Int32> [-PlacementConstraint <String>] [-Metric <String[]>]
 [-Correlation <String[]>] [-PlacementPolicy <String[]>] -ServiceGroupMemberDescription <Hashtable[]>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Stateless UniformInt64 Adhoc
```
New-ServiceFabricServiceGroup [-Stateless] [-PartitionSchemeUniformInt64] [-Adhoc] [-ServiceName] <Uri>
 [-ServiceTypeName] <String> -PartitionCount <Int32> -LowKey <Int64> -HighKey <Int64> -InstanceCount <Int32>
 [-PlacementConstraint <String>] [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 -ServiceGroupMemberDescription <Hashtable[]> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ServiceFabricServiceGroup** cmdlet creates a Service Fabric service group.
This cmdlet is similar to the New-ServiceFabricService cmdlet, except that this cmdlet creates a service group, and **New-ServiceFabricService** creates a service.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Create a stateful service group
```
PS C:\>New-ServiceFabricServiceGroup -ApplicationName fabric:/myapp/persistenttodolist -ServiceName fabric:/myapp/persistenttodolist/svc1 -ServiceTypeName "PersistentToDoListServiceGroupType" -Stateful -PartitionSchemeSingleton -TargetReplicaSetSize 3 -MinReplicaSetSize 2 -ServiceGroupMemberDescription @(@{"ServiceName"="fabric:/myapp/persistenttodolist/svc1#a";"ServiceTypeName"=" PersistentToDoListServiceGroupTypeA"},@{"ServiceName"="fabric:/myapp/persistenttodolist/svc1#b";"ServiceTypeName"=" PersistentToDoListServiceGroupTypeB"})
```

This command creates a Service Fabric stateful service group from the specified application instance by using a singleton partition scheme.

## PARAMETERS

### -Adhoc
Indicates that the service runs in ad hoc mode.
In ad hoc mode, you manually activate the service host.

```yaml
Type: SwitchParameter
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful Singleton Adhoc, Stateful Named Adhoc, Stateless Named Adhoc, Stateless Singleton Adhoc, Stateless UniformInt64 Adhoc
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet creates a service group based on the application that has the URI that you specify.

```yaml
Type: Uri
Parameter Sets: Stateless Singleton Non-Adhoc, Stateful Singleton Non-Adhoc, Stateful UniformInt64 Non-Adhoc, Stateful Named Non-Adhoc, Stateless UniformInt64 Non-Adhoc, Stateless Named Non-Adhoc
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Correlation
Specifies an array of correlation constraints for this service.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HasPersistedState
Indicates that the stateful service has persistent state.

```yaml
Type: SwitchParameter
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful Singleton Non-Adhoc, Stateful UniformInt64 Non-Adhoc, Stateful Named Non-Adhoc, Stateful Singleton Adhoc, Stateful Named Adhoc
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighKey
Specifies the high-key range of the partition set.

```yaml
Type: Int64
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful UniformInt64 Non-Adhoc, Stateless UniformInt64 Non-Adhoc, Stateless UniformInt64 Adhoc
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceCount
Specifies the number of instances for the stateless service.

```yaml
Type: Int32
Parameter Sets: Stateless Singleton Non-Adhoc, Stateless Named Adhoc, Stateless UniformInt64 Non-Adhoc, Stateless Named Non-Adhoc, Stateless Singleton Adhoc, Stateless UniformInt64 Adhoc
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowKey
Specifies the low-key range of the partition set.

```yaml
Type: Int64
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful UniformInt64 Non-Adhoc, Stateless UniformInt64 Non-Adhoc, Stateless UniformInt64 Adhoc
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metric
Specifies an array of metrics that the service reports.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinReplicaSetSize
Specifies the minimum replica set size for the Service Fabric stateful service.

```yaml
Type: Int32
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful Singleton Non-Adhoc, Stateful UniformInt64 Non-Adhoc, Stateful Named Non-Adhoc, Stateful Singleton Adhoc, Stateful Named Adhoc
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionCount
Specifies the number of partition counts for the service.

```yaml
Type: Int32
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful UniformInt64 Non-Adhoc, Stateless UniformInt64 Non-Adhoc, Stateless UniformInt64 Adhoc
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionNames
Specifies an array of names of partitions.

```yaml
Type: String[]
Parameter Sets: Stateful Named Non-Adhoc, Stateful Named Adhoc, Stateless Named Adhoc, Stateless Named Non-Adhoc
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionSchemeNamed
Indicates that the service uses the named partition scheme.

```yaml
Type: SwitchParameter
Parameter Sets: Stateful Named Non-Adhoc, Stateful Named Adhoc, Stateless Named Adhoc, Stateless Named Non-Adhoc
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionSchemeSingleton
Indicates that the service uses the singleton partition scheme.

```yaml
Type: SwitchParameter
Parameter Sets: Stateless Singleton Non-Adhoc, Stateful Singleton Non-Adhoc, Stateful Singleton Adhoc, Stateless Singleton Adhoc
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionSchemeUniformInt64
Indicates that the service uses the UniformInt64 partition scheme.

```yaml
Type: SwitchParameter
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful UniformInt64 Non-Adhoc, Stateless UniformInt64 Non-Adhoc, Stateless UniformInt64 Adhoc
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlacementConstraint
Specifies the placement constraint for the service.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlacementPolicy
Specifies an array of placement policies for a service.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuorumLossWaitDuration
Specifies the duration, as a **TimeSpan** object, that Service Fabric waits before it declares data loss for the service partition.
To obtain a **TimeSpan** object, use the [New-TimeSpan](http://go.microsoft.com/fwlink/?LinkID=113360) cmdlet.
For more information, type `Get-Help New-TimeSpan`.

```yaml
Type: TimeSpan
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful Singleton Non-Adhoc, Stateful UniformInt64 Non-Adhoc, Stateful Named Non-Adhoc, Stateful Singleton Adhoc, Stateful Named Adhoc
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaRestartWaitDuration
Specifies the interval, as a **TimeSpan** object, that Service Fabric waits for the replica to restart before it fails over the replica.
To obtain a **TimeSpan** object, use the **New-TimeSpan** cmdlet.

```yaml
Type: TimeSpan
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful Singleton Non-Adhoc, Stateful UniformInt64 Non-Adhoc, Stateful Named Non-Adhoc, Stateful Singleton Adhoc, Stateful Named Adhoc
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceGroupMemberDescription
Indicates the member configurations of a service group.
Specify the value for this parameter in the following format:

@(@{"ServiceName"=\<serviceName\>;"ServiceTypeName"=\<serviceType\>;"LoadMetrics"=\<metrics\>}).

For example: @(@{"ServiceName"="fabric:/myapp/calculator/svc1;"ServiceTypeName"="CalculatorServiceType"})

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the URI of a Service Fabric service group.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceTypeName
Specifies the name of a Service Fabric service type.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stateful
Indicates that the service is a Service Fabric stateful service.

```yaml
Type: SwitchParameter
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful Singleton Non-Adhoc, Stateful UniformInt64 Non-Adhoc, Stateful Named Non-Adhoc, Stateful Singleton Adhoc, Stateful Named Adhoc
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stateless
Indicates that the service is a Service Fabric stateless service.

```yaml
Type: SwitchParameter
Parameter Sets: Stateless Singleton Non-Adhoc, Stateless Named Adhoc, Stateless UniformInt64 Non-Adhoc, Stateless Named Non-Adhoc, Stateless Singleton Adhoc, Stateless UniformInt64 Adhoc
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetReplicaSetSize
Specifies the target replica set size for a Service Fabric stateful service.

```yaml
Type: Int32
Parameter Sets: Stateful UniformInt64 Adhoc, Stateful Singleton Non-Adhoc, Stateful UniformInt64 Non-Adhoc, Stateful Named Non-Adhoc, Stateful Singleton Adhoc, Stateful Named Adhoc
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Description.ServiceGroupDescription** object for a Service Fabric service.

## NOTES

## RELATED LINKS

[Remove-ServiceFabricServiceGroup](./Remove-ServiceFabricServiceGroup.md)

[Update-ServiceFabricServiceGroup](./Update-ServiceFabricServiceGroup.md)
