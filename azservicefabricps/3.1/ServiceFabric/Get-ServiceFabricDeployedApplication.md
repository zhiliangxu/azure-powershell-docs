---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 7F501BC1-A1CB-4C45-B4CD-DB4DF2001CA4
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedApplication.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedApplication.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricDeployedApplication

## SYNOPSIS
Gets a Service Fabric application on a node.

## SYNTAX

```
Get-ServiceFabricDeployedApplication [-NodeName] <String> [[-ApplicationName] <Uri>] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricDeployedApplication** cmdlet gets a Service Fabric application deployed on a specified node.

Service Fabric creates work, log, and temporary directories on the node for each deployed application.
Because the directory names include the application ID, the directory names cannot be guessed.
When the **DeployedApplicationStatus** is Active, **Get-ServiceFabricDeployedApplication** returns the directory names in the **WorkDirectory**, **LogDirectory**, and **TempDirectory** return values.
When the **DeployedApplicationStatus** is Downloading, the **WorkDirectory**, **LogDirectory**, and **TempDirectory** values are null.

The deployed application services store their persisted data in the **WorkDirectory**.
For debugging or diagnostic purposes a different application or process may need to know the location of the **WorkDirectory**.

The deployed application services should store their log in the **LogDirectory** created by Service Fabric.
A custom uploader of the log files may need to know the location.
The location of the **LogDirectory** may be needed for diagnostic purposes as well when an application on a particular node is not working as expected.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get active application
```
PS C:\>Get-ServiceFabricDeployedApplication -NodeName "VIPULM4-RK01-BD01" -ApplicationName fabric:/samples/CalcApp2
ApplicationName           : fabric:/samples/CalcApp2

ApplicationTypeName       : CalculatorApp

DeployedApplicationStatus : Active

WorkDirectory             : D:\ServiceFabric\Data\VIPULM4-RK01-BD01\Fabric\work\Applications\CalculatorApp_App5\work

LogDirectory              : D:\ServiceFabric\Data\VIPULM4-RK01-BD01\Fabric\work\Applications\CalculatorApp_App5\log

TempDirectory             : D:\ServiceFabric\Data\VIPULM4-RK01-BD01\Fabric\work\Applications\CalculatorApp_App5\temp
```

This command returns deployed applications.
In this example, the **DeployedApplicationStatus** is Active, and, therefore, **Get-ServiceFabricDeployedApplication** returns the directory names in the **WorkDirectory**, **LogDirectory**, and **TempDirectory** return values.

### Example 2: Get downloading application
```
PS C:\>Get-ServiceFabricDeployedApplication -NodeName VIPULM4-RK01-BD01 fabric:/samples/VQueueApp2
ApplicationName           : fabric:/samples/VQueueApp2

ApplicationTypeName       : VolatileQueueApp

DeployedApplicationStatus : Downloading
```

This command returns deployed applications.
In this example, the **DeployedApplicationStatus** is Downloading, and, therefore, the command returns values of null for **WorkDirectory**, **LogDirectory**, and **TempDirectory**.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet gets the application that has the URI that you specify.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet gets applications deployed on the node that you specify.

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

### System.Uri, String
This cmdlet accepts a URI that represents the name of the Service Fabric application, or a string representing the Service Fabric node name.

## OUTPUTS

### System.Object
This cmdlet returns the **System.Fabric.Query.DeployedApplication** objects that represent the deployed applications in the cluster.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricApplication](./Get-ServiceFabricApplication.md)
