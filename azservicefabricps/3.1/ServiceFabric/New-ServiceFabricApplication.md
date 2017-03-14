---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 5CF5310E-E6BC-4F08-858A-DC9CF5FC0493
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricApplication.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricApplication.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-ServiceFabricApplication

## SYNOPSIS
Creates a Service Fabric application.

## SYNTAX

```
New-ServiceFabricApplication [-ApplicationName] <Uri> [-ApplicationTypeName] <String>
 [-ApplicationTypeVersion] <String> [-ApplicationParameter <Hashtable>] [-MaximumNodes <Int64>]
 [-MinimumNodes <Int64>] [-TimeoutSec <Int32>] [-Metrics <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ServiceFabricApplication** cmdlet creates a Service Fabric application of a registered application type.
Use the [Register-ServiceFabricApplicationType](.\Register-ServiceFabricApplicationType.md) cmdlet to register an application type.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Create an application
```
PS C:\>New-ServiceFabricApplication -ApplicationName fabric:/myapp/persistenttodolist -ApplicationTypeName "PersistentToDoListApp" -ApplicationTypeVersion "1.0"
```

This command creates an application of the type PersistentToDoListApp.
The application is version 1.0.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet creates a Service Fabric application with the name that you specify.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationParameter
Specifies the overrides for application parameters as name/value pairs.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeName
Specifies the name of a Service Fabric application type.
The cmdlet creates a Service Fabric application of the application type that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeVersion
Specifies the version of a Service Fabric application type.
The cmdlet creates an application that has the version that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumNodes
Specifies the maximum number of nodes on which to place an application.
The value of this parameter must be a non-negative integer.

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

### -Metrics
Specifies an array of metrics.
Each metric can follow the pattern MetricName,NodeReservationCapacity,MaximumNodeCapacity,TotalApplicationCapacity, or can specify MetricName and use parameter names NodeReservationCapacity,MaximumNodeCapacity,TotalApplicationCapacity followed by a parameter value, and separated with a colon.
Each parameter **name:value** pair can appear at most once.

- MetricName.
Specifies the name of the metric.
- NodeReservationCapacity.
Specifies the amount of metric load that is reserved on nodes that have instances of this application.
If *MinimumNodes* is specified, the product of these values is the capacity reserved in the cluster for the application.
- MaximumNodeCapacity.
Specifies the maximum load for an instance of this application on a single node.
Even if the capacity of the node is greater than this value, Service Fabric limits the total load of the application's child replicas to this value.
- TotalApplicationCapacity.
Specifies the total capacity for the application in the cluster.
Service Fabric attempts to limit the sum of loads of the application's child replicas to this value.

While creating the application, Service Fabric performs the following validations and will fail the command if they do not pass:

- NodeReservationCapacity must not be more than MaximumNodeCapacity.

- If both the *MinimumNodes* parameter and NodeReservationCapacity metric are specified, then the product of *MinimumNodes* and NodeReservationCapacity must not be more than TotalApplicationCapacity.

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

### -MinimumNodes
Specifies the number of nodes on which capacity is reserved for this application.
The value of this parameter must be a non-negative integer.

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
This cmdlet returns a **System.Fabric.Description.ApplicationDescription** object for a Service Fabric application.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricApplication](./Get-ServiceFabricApplication.md)

[Remove-ServiceFabricApplication](./Remove-ServiceFabricApplication.md)

[Register-ServiceFabricApplicationType](./Register-ServiceFabricApplicationType.md)
