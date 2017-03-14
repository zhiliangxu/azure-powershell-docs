---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: FBF3750F-5967-46CF-A6F0-AE01BDB56795
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedCodePackage.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedCodePackage.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricDeployedCodePackage

## SYNOPSIS
Gets the Service Fabric code packages deployed on a node.

## SYNTAX

```
Get-ServiceFabricDeployedCodePackage [-NodeName] <String> [-ApplicationName] <Uri>
 [[-ServiceManifestName] <String>] [[-CodePackageName] <String>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricDeployedCodePackage** cmdlet gets the Service Fabric code package deployed on a specified node.
You can specify a service manifest name or code package name.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get all deployed code packages
```
PS C:\>Get-ServiceFabricDeployedCodePackage -NodeName "Node01" -ApplicationName fabric:/MyApplication
```

This command gets all deployed code packages for application fabric:/MyApplication on node Node01.

### Example 2: Get all deployed code packages filtered by service manifest name
```
PS C:\>Get-ServiceFabricDeployedCodePackage -NodeName "Node01" -ApplicationName fabric:/MyApplication -ServiceManifestName "CalcServicePackage"
```

This command gets all deployed code packages for application fabric:/MyApplication on node Node01 for service manifest CalcServicePackage.

### Example 3: Get the specified deployed code package
```
PS C:\>Get-ServiceFabricDeployedCodePackage -NodeName "Node01" -ApplicationName fabric:/MyApplication -ServiceManifestName "CalcServicePackage" -CodePackageName "CalcCodePackage"
```

This command gets the deployed code package for application fabric:/MyApplication on node Node01 for service manifest CalcServicePackage and code package CalcCodePackage.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet gets the code package for the application that you specify.

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

### -CodePackageName
Specifies the name of a Service Fabric code package.
The cmdlet gets the code package that you specify.
If you do not specify this parameter, this cmdlet returns all code packages that match the other specified parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet gets the code package deployed to the node that you specify.

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

### -ServiceManifestName
Specifies the name of a Service Fabric service manifest.
The cmdlet gets the code package for the service manifest that you specify.
If you do not specify this parameter, this cmdlet returns code packages for all service filters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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
This cmdlet accepts a URI that represents the name of the Service Fabric application, or a string that represents a Service Fabric node name where the code packages are deployed, or a string that represents filters for service manifest name or code package name.

## OUTPUTS

### System.Object
This cmdlet returns **DeployedCodePackage** object that represent deployed code packages.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
