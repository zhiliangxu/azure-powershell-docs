---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: F4B3017C-09C6-4423-ADC0-9F49F3F8AFB7
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedServicePackageHealth.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedServicePackageHealth.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricDeployedServicePackageHealth

## SYNOPSIS
Gets the health of a Service Fabric service package.

## SYNTAX

```
Get-ServiceFabricDeployedServicePackageHealth [-ApplicationName] <Uri> [-ServiceManifestName] <String>
 [-NodeName] <String> [-ConsiderWarningAsError <Boolean>] [-EventsHealthStateFilter <Int64>]
 [-EventsFilter <HealthStateFilter>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricDeployedServicePackageHealth** cmdlet gets the health of a Service Fabric service package deployed on a specified node.
Service Fabric reports the following health states:

- OK.
The entity meets health guidelines.
- Error.
The entity does not meet health guidelines.
- Warning.
The entity meets health guidelines but experienced some issue.

If the application is not deployed on the specified node, this cmdlet returns error.
If the deployed service package does not exist, this cmdlet returns error.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the health of a deployed service package
```
PS C:\>Get-ServiceFabricDeployedServicePackageHealth -ApplicationName fabric:/myapp/persistenttodolist -NodeName "Node01" -ServiceManifestName "ServicePackageA"
```

This command queries the health of the specified deployed service package.

### Example 2: Get the health of a deployed service package using custom health policy and return filters
```
PS C:\>Get-ServiceFabricDeployedServicePackageHealth -ApplicationName fabric:/myapp/persistenttodolist -NodeName "Node01" -ServiceManifestName "ServicePackageA" -ConsiderWarningAsError $True -EventsFilter Error
```

This command queries the health of the specified deployed service package with custom health policy and error events filter.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet gets health information for the deployed service package of the application that you specify.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

### -EventsFilter
Specifies the filter for the collection of **HealthEvent**s reported on the service package based on health state.
The value can be obtained from members or bitwise operations on members of **HealthStateFilter**.
Only events that match the filter are returned.
All events are used to evaluate the service package aggregated health state.
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
The cmdlet gets health information for the service package for the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceManifestName
Specifies the name of a Service Fabric service manifest.
The cmdlet gets health information for the service manifest that you specify.

```yaml
Type: String
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

### System.Uri, String
This cmdlet accepts a URI that represents the name of a Service Fabric application, or a Service Fabric node name, or a service manifest name.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Health.DeployedServicePackageHealth** object that represents the health of a deployed service package.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricDeployedServicePackage](./Get-ServiceFabricDeployedServicePackage.md)
