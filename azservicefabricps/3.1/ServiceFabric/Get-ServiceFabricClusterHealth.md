---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 254DBEA6-4651-47EA-B023-74D74B0251E2
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricClusterHealth.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricClusterHealth.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricClusterHealth

## SYNOPSIS
Gets health information for a Service Fabric cluster.

## SYNTAX

```
Get-ServiceFabricClusterHealth [-ConsiderWarningAsError <Boolean>] [-MaxPercentUnhealthyApplications <Byte>]
 [-MaxPercentUnhealthyNodes <Byte>] [-EventsHealthStateFilter <Int64>] [-EventsFilter <HealthStateFilter>]
 [-ApplicationsHealthStateFilter <Int64>] [-ApplicationsFilter <HealthStateFilter>]
 [-NodesHealthStateFilter <Int64>] [-NodesFilter <HealthStateFilter>]
 [-ApplicationHealthPolicyMap <ApplicationHealthPolicyMap>]
 [-ApplicationTypeHealthPolicyMap <ApplicationTypeHealthPolicyMap>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricClusterHealth** cmdlet gets health information for a Service Fabric cluster.
Service Fabric reports the following health states:

- OK.
The entity meets health guidelines.
- Error.
The entity does not meet health guidelines.
- Warning.
The entity meets health guidelines but experienced some issue.

The aggregated health state of the cluster takes into consideration all health reports on the cluster as well as the aggregated health state of all children, recursively.
The health evaluation uses the cluster health policy and the application health policy of each application in the cluster.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the health of the cluster and filter returned children
```
PS C:\>Get-ServiceFabricClusterHealth -NodesFilter Error -ApplicationsFilter 'Warning,Error'
```

This command queries the health of the cluster.
It specifies filters to return only nodes with health state Error and applications with health state Warning or Error.

### Example 2: Get the health of the cluster using custom health policies
```
PS C:\>$defaultServiceTypeHealthPolicy = new-object -TypeName System.Fabric.Health.ServiceTypeHealthPolicy
$defaultServiceTypeHealthPolicy.MaxPercentUnhealthyPartitionsPerService = 20
$defaultServiceTypeHealthPolicy.MaxPercentUnhealthyServices = 10
$appHealthPolicy = New-Object -TypeName System.Fabric.Health.ApplicationHealthPolicy
$appHealthPolicy.ConsiderWarningAsError = $True
$appHealthPolicy.MaxPercentUnhealthyDeployedApplications = 20
$appHealthPolicy.DefaultServiceTypeHealthPolicy = $defaultServiceTypeHealthPolicy
$appHealthPolicyMap = New-Object -TypeName System.Fabric.Health.ApplicationHealthPolicyMap
$appUri1 = New-Object -TypeName System.Uri -ArgumentList "fabric:/app1"
$appHealthPolicyMap.Add($appUri1, $appHealthPolicy)
Get-ServiceFabricClusterHealth -ConsiderWarningAsError $True -MaxPercentUnhealthyNodes 10 -ApplicationHealthPolicyMap $appHealthPolicyMap
```

This command queries the health of the cluster and passes in custom policies.

### Example 3: Get the health of the cluster using an application type health policy map
```
PS C:\>$AppTypeHealthPolicyMap = New-Object -TypeName "System.Fabric.Health.ApplicationTypeHealthPolicyMap"
PS C:\> $AppTypeHealthPolicyMap.Add("CriticalAppType", 0)
PS C:\> Get-ServiceFabricClusterHealth -ApplicationTypeHealthPolicyMap $AppTypeHealthPolicyMap -MaxPercentUnhealthyApplications 20
```

This command queries the health of the cluster and passes in an application type health policy map.
The application type CriticalAppType does not tolerate any failures.
The remaining applications are evaluated using 20% maximum percent unhealthy.

## PARAMETERS

### -ApplicationHealthPolicyMap
Specifies the **ApplicationHealthPolicyMap** that includes custom health policies for some or all of the applications.
If you do not specify this parameter, the health evaluation uses the application health policies defined in the application manifest or the default health policy.

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

For example, if some applications of a type are critical, the cluster administrator can add an entry to the map for that application type and assign it a value of 0% (that is, do not tolerate any failures).
All other applications can be evaluated with *MaxPercentUnhealthyApplications* set to 20% to tolerate some failures out of the thousands of application instances.

The application type health policy map is used only if the cluster manifest enables application type health evaluation using the configuration entry for **HealthManager/EnableApplicationTypeHealthEvaluation**.

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

### -ApplicationsFilter
Specifies the filter for **ApplicationHealthState** children based on health state.
The value can be obtained from members or bitwise operations on members of **HealthStateFilter**.
Only children that match the filter are returned.
All children will be used to evaluate the entity aggregated health state.
If not specified, all entries will be returned.

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

### -ApplicationsHealthStateFilter
This parameter has been deprecated.
Specify the *ApplicationsFilter* parameter instead.

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

### -ConsiderWarningAsError
Indicates whether to treat a warning health report as error during health evaluation.
This value is used for evaluation of nodes and cluster health reports.

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
Specifies the filter for the collection of **HealthEvent**s reported on the cluster based on health state.
The value can be obtained from members or bitwise operations on members of **HealthStateFilter**.
Only events that match the filter are returned.
All events are used to evaluate the aggregated health state of the cluster.
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

### -MaxPercentUnhealthyApplications
Specifies the maximum tolerated percentage of unhealthy applications.
If there are more applications with aggregated health state of error than tolerated, the health state of the cluster is error.
If you do not specify this parameter, the health evaluation uses the value provided in the cluster manifest.

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
If there are more nodes with aggregated health state of error than tolerated, the cluster is evaluated as error.
If you do not specify this parameter, the health evaluation uses the value provided in the cluster manifest.

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

### -NodesFilter
Specifies the filter for **NodeHealthState** children based on health state.
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

### -NodesHealthStateFilter
This parameter has been deprecated.
Specify the *NodesFilter* parameter instead.

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

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Health.ClusterHealth** object that represents the health of the Service Fabric cluster.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
