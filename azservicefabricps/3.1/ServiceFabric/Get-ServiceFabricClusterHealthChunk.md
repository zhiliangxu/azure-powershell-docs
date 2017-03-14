---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 7EE2AE48-02B7-4A75-B20F-75AA942A4C96
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricClusterHealthChunk.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricClusterHealthChunk.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricClusterHealthChunk

## SYNOPSIS
Gets health information for a Service Fabric cluster and its children.

## SYNTAX

```
Get-ServiceFabricClusterHealthChunk [-ConsiderWarningAsError <Boolean>]
 [-MaxPercentUnhealthyApplications <Byte>] [-MaxPercentUnhealthyNodes <Byte>]
 [-ApplicationHealthPolicies <ApplicationHealthPolicyMap>]
 [-ApplicationTypeHealthPolicyMap <ApplicationTypeHealthPolicyMap>]
 [-ApplicationFilters <System.Collections.Generic.List`1[System.Fabric.Health.ApplicationHealthStateFilter]>]
 [-NodeFilters <System.Collections.Generic.List`1[System.Fabric.Health.NodeHealthStateFilter]>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricClusterHealthChunk** cmdlet gets health information for a Service Fabric cluster and cluster entities as requested with the advanced input filters.
By default, no child entities are returned.
If specified, all entities that respect the input are returned in a hierarchical fashion.

Service Fabric reports the following health states.

- OK.
The entity meets health guidelines.
- Error.
The entity does not meet health guidelines.
- Warning.
The entity meets health guidelines but is experiencing some issues.

The aggregated health state of the cluster takes into consideration all health reports on the cluster as well as the aggregated health state of all children, recursively.
The health evaluation uses the cluster health policy and the application health policy of each application in the cluster.
You can pass the health policies for cluster and for application evaluation as input.
If not specified, health evaluation uses the applicable health policies from the cluster and application manifest if the manifest is specified, or the default policies otherwise.

The cluster health chunk includes only children of interest as specified in the input filters.
The filtering is done on the server side, so message size is minimized.

If the requested output does not fit into a message, no result is returned.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the health of the cluster with node filters
```
PS C:\>$ErrorFilter = [System.Fabric.Health.HealthStateFilter]::Error;
PS C:\> $AllFilter = [System.Fabric.Health.HealthStateFilter]::All;
PS C:\> $NodeFilter1 = New-Object System.Fabric.Health.NodeHealthStateFilter -Property @{HealthStateFilter=$AllFilter}
PS C:\> $NodeFilter2 = New-Object System.Fabric.Health.NodeHealthStateFilter -Property @{NodeNameFilter="N0010";HealthStateFilter=$ErrorFilter}
PS C:\> $NodeFilters = New-Object System.Collections.Generic.List[System.Fabric.Health.NodeHealthStateFilter]
PS C:\> $NodeFilters.Add($NodeFilter1)
PS C:\> $NodeFilters.Add($NodeFilter2)
PS C:\> Get-ServiceFabricClusterHealthChunk -NodeFilter $NodeFilters
```

This command queries the health of the cluster.
It specifies filters to return all nodes, except for node N0010, which should be included only if its aggregated health state in Error.

### Example 2: Get the health of the cluster with deployed entity filters
```
PS C:\>$ErrorFilter = [System.Fabric.Health.HealthStateFilter]::Error;
PS C:\> $AllFilter = [System.Fabric.Health.HealthStateFilter]::All;
PS C:\> $DspFilter1 = New-Object System.Fabric.Health.DeployedServicePackageHealthStateFilter -Property @{HealthStateFilter=$AllFilter}
PS C:\> $DaFilter1 =  New-Object System.Fabric.Health.DeployedApplicationHealthStateFilter -Property @{HealthStateFilter=$AllFilter;NodeNameFilter="N0020"}
PS C:\> $DaFilter1.DeployedServicePackageFilters.Add($DspFilter1)
PS C:\> $AppFilter = New-Object System.Fabric.Health.ApplicationHealthStateFilter -Property @{HealthStateFilter=$AllFilter}
PS C:\> $AppFilter.DeployedApplicationFilters.Add($DaFilter1)
PS C:\> $AppFilters = New-Object System.Collections.Generic.List[System.Fabric.Health.ApplicationHealthStateFilter]
PS C:\> $AppFilters.Add($AppFilter)
PS C:\> Get-ServiceFabricClusterHealthChunk -ApplicationFilters $AppFilters
```

This command queries the health of the cluster.
It specifies filters to return all applications and deployed applications and deployed service packages on a specified node (N0020).

### Example 3: Get the health of the cluster with an application filter that includes recursive inner filters
```
PS C:\>$ErrorFilter = [System.Fabric.Health.HealthStateFilter]::Error;
PS C:\> $AllFilter = [System.Fabric.Health.HealthStateFilter]::All;
PS C:\> $ReplicaFilter1 = New-Object System.Fabric.Health.ReplicaHealthStateFilter -Property @{ReplicaOrInstanceIdFilter= 130984777977143495;HealthStateFilter=$ErrorFilter}
PS C:\> $ReplicaFilter2 = New-Object System.Fabric.Health.ReplicaHealthStateFilter -Property @{HealthStateFilter=$AllFilter}

PS C:\> $PartitionFilter = New-Object System.Fabric.Health.PartitionHealthStateFilter -Property @{HealthStateFilter=$AllFilter}
PS C:\> $PartitionFilter.ReplicaFilters.Add($ReplicaFilter1)
PS C:\> $PartitionFilter.ReplicaFilters.Add($ReplicaFilter2)

PS C:\> $SvcFilter1 = New-Object System.Fabric.Health.ServiceHealthStateFilter -Property @{HealthStateFilter=$AllFilter}
PS C:\> $SvcFilter1.PartitionFilters.Add($PartitionFilter)

PS C:\> $AppFilter = New-Object System.Fabric.Health.ApplicationHealthStateFilter -Property @{ApplicationNameFilter="fabric:/app1"}
PS C:\> $AppFilter.ServiceFilters.Add($SvcFilter1)

PS C:\> $AppFilters = New-Object System.Collections.Generic.List[System.Fabric.Health.ApplicationHealthStateFilter]
PS C:\> $AppFilters.Add($AppFilter)
PS C:\> Get-ServiceFabricClusterHealthChunk -ApplicationFilters $AppFilters
```

This command queries the health of the cluster.
It specifies filters to return only an application.
The filter returns all application services, and for each service, it returns all partitions.
For each partition, it includes all replicas, except for 130984777977143495, which should only be returned if it's at Error.

## PARAMETERS

### -ApplicationFilters
Specifies a **Systems.Collections.Generic.List** of **System.Fabric.Health.ApplicationHealthStateFilter** objects.
Only applications that respect the most specific filter are returned.
You can specify the filters for individual applications or for all applications.
Only one general filter and one filter per application are allowed.

If you do not specify this parameter, no applications are returned.

```yaml
Type: System.Collections.Generic.List`1[System.Fabric.Health.ApplicationHealthStateFilter]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationHealthPolicies
Specifies a **System.Fabric.Health.ApplicationHealthPolicyMap** that includes custom health policies for some or all of the applications.
If you do not specify this parameter, or if you don't include an entry in the map for an application, that application is evaluated with the application health policy defined in the application manifest if it exists, or the default policy otherwise.

```yaml
Type: ApplicationHealthPolicyMap
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeHealthPolicyMap
Specifies the map that defines the maximum percentage of unhealthy applications that are allowed per application type.
Application types in this map are evaluated using specific percentages rather than the global *MaxPercentUnhealthyApplications* percentage.

For instance, if some applications of a type are critical, the cluster administrator can add an entry to the map for that application type and assign it a value of 0% (that is, do not tolerate any failures).
All other applications can be evaluated with *MaxPercentUnhealthyApplications* set to 20% to tolerate some failures out of the thousands of application instances.

The application type health policy map is used only if the cluster manifest enables application type health evaluation using the configuration entry for HealthManager/EnableApplicationTypeHealthEvaluation.

```yaml
Type: ApplicationTypeHealthPolicyMap
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsiderWarningAsError
Indicates whether to treat a warning health report as an error during health evaluation.
This value is used for evaluation of nodes and cluster health reports.

If none of the cluster health policy parameters are specified, health evaluation uses the cluster health policy from the cluster manifest, if it exists, or the default policy that tolerates no failures.

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

### -MaxPercentUnhealthyApplications
Specifies the maximum tolerated percentage of unhealthy applications.
If there are more applications with aggregated health state of error than tolerated, the health state of the cluster is Error.

If none of the cluster health policy parameters are specified, health evaluation uses the cluster health policy from the cluster manifest, if it exists, or the default policy that tolerates no failures.

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

### -MaxPercentUnhealthyNodes
Specifies the maximum tolerated percentage of unhealthy nodes.
If there are more nodes with aggregated health state of error than tolerated, the cluster is evaluated as Error.
If you do not specify this parameter, the health evaluation uses the value provided in the cluster manifest.

If none of the cluster health policy parameters are specified, health evaluation uses the cluster health policy from the cluster manifest, if it exists, or the default policy that tolerates no failures.

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

### -NodeFilters
Specifies a **Systems.Collections.Generic.List** of **System.Fabric.Health.NodeHealthStateFilter** objects.
Only nodes that respect the most specific filter are returned.
You can specify the filters for individual nodes or for all nodes.
Only one general filter and one filter per node are allowed.
If you do not specify this parameter, no nodes are returned.

```yaml
Type: System.Collections.Generic.List`1[System.Fabric.Health.NodeHealthStateFilter]
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

###  
None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Health.ClusterHealthChunk** object that represents the health of the Service Fabric cluster.

## NOTES

## RELATED LINKS
