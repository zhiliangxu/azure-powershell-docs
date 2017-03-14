---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: E595285A-E976-4071-B085-C414D125F9B9
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedApplicationHealth.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedApplicationHealth.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricDeployedApplicationHealth

## SYNOPSIS
Gets the health of a Service Fabric application on a node.

## SYNTAX

```
Get-ServiceFabricDeployedApplicationHealth [-NodeName] <String> [-ApplicationName] <Uri>
 [-ConsiderWarningAsError <Boolean>] [-EventsHealthStateFilter <Int64>] [-EventsFilter <HealthStateFilter>]
 [-DeployedServicePackagesHealthStateFilter <Int64>] [-DeployedServicePackagesFilter <HealthStateFilter>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricDeployedApplicationHealth** cmdlet gets the health of Service Fabric applications deployed on a node in a cluster.
Service Fabric reports the following health states:

- OK.
The entity meets health guidelines.
- Error.
The entity does not meet health guidelines.
- Warning.
The entity meets health guidelines but experienced some issue.

If the application is not deployed on the specified node, this cmdlet returns an error.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the health of a deployed application
```
PS C:\>Get-ServiceFabricDeployedApplicationHealth -ApplicationName fabric:/myapp/persistenttodolist -NodeName "Node01"
```

This command queries the health of the named application deployed on node named Node01.

### Example 2: Get the health of a deployed application using custom health policy and return filters
```
PS C:\>Get-ServiceFabricDeployedApplicationHealth -ApplicationName fabric:/myapp/persistenttodolist -NodeName "Node01" -ConsiderWarningAsError $True -EventsFilter Error -DeployedServicePackagesFilter 'Warning,Error'
```

This command queries the health of the named application deployed on node Node01.
It specifies values for health policy.
It uses filters to return only Error events, and children with Error or Warning health states.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet gets health information for the application that has the URI that you specify.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -DeployedServicePackagesFilter
Specifies the filter for **DeployedServicePackageHealthState** children based on health state.
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

### -DeployedServicePackagesHealthStateFilter
This parameter has been deprecated.
Specify the *DeployedServicePackagesFilter* instead.

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

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet gets health information for the application deployed to the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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
This cmdlet accepts a URI that represents the name of the Service Fabric application, or a string representing the Service Fabric node name.

## OUTPUTS

### System.Object
This cmdlet returns the **System.Fabric.Health.DeployedApplicationHealth** object that represents the health of a deployed applications.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricDeployedApplication](./Get-ServiceFabricDeployedApplication.md)
