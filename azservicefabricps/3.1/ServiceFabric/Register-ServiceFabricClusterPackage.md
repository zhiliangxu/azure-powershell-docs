---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 4E889F33-E989-492D-884A-A59A3A89FE08
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Register-ServiceFabricClusterPackage.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Register-ServiceFabricClusterPackage.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Register-ServiceFabricClusterPackage

## SYNOPSIS
Registers a Service Fabric cluster package.

## SYNTAX

### Both (Default)
```
Register-ServiceFabricClusterPackage -CodePackagePath <String> -ClusterManifestPath <String>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Code
```
Register-ServiceFabricClusterPackage [-Code] -CodePackagePath <String> [-ClusterManifestPath <String>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Config
```
Register-ServiceFabricClusterPackage [-Config] [-CodePackagePath <String>] -ClusterManifestPath <String>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Register-ServiceFabricClusterPackage** cmdlet registers a Service Fabric clustermanifest and/or a Service Fabric .msi.

To manage Service Fabric clusters, start Windows PowerShell by using the Run as administrator option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Register a package that contains both code and configuration
```
PS C:\>Register-ServiceFabricClusterPackage -ClusterManifestPath "ClusterManifest_123.xml" -CodePackagePath "ServiceFabric.2.0.59.0.msi"
```

This command registers a package that contains both .msi and configuration information.

### Example 2: Register a package that contains only configuration
```
PS C:\>Register-ServiceFabricClusterPackage -Config -ClusterManifestPath "ClusterManifest_123.xml"
```

This command registers a package that contains only configuration information.
The command includes the **Config** parameter, so the command applies to a manifest only.

## PARAMETERS

### -ClusterManifestPath
Specifies the path of a Service Fabric cluster manifest in the ImageStore.
The cmdlet registers file at the path that you specify.

```yaml
Type: String
Parameter Sets: Both, Config
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Code
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Code
Indicates that the package includes only a Service Fabric .msi file in the ImageStore.

```yaml
Type: SwitchParameter
Parameter Sets: Code
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CodePackagePath
Specifies the file path of the Service Fabric .msi file.
The cmdlet registers the file in the path that you specify.

```yaml
Type: String
Parameter Sets: Both, Code
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Config
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Config
Indicates that the package is a Service Fabric cluster manifest.

```yaml
Type: SwitchParameter
Parameter Sets: Config
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

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns the status of the operation as a string.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Copy-ServiceFabricClusterPackage](./Copy-ServiceFabricClusterPackage.md)

[Unregister-ServiceFabricClusterPackage](./Unregister-ServiceFabricClusterPackage.md)
