---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: CF0A03A9-D1E2-446A-BCA2-80B1D620D586
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricClusterPackage.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricClusterPackage.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-ServiceFabricClusterPackage

## SYNOPSIS
Removes a Service Fabric cluster package from the image store.

## SYNTAX

### Code
```
Remove-ServiceFabricClusterPackage [-Code] -CodePackagePathInImageStore <String>
 [-ClusterManifestPathInImageStore <String>] -ImageStoreConnectionString <String> [-TimeoutSec <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Config
```
Remove-ServiceFabricClusterPackage [-Config] [-CodePackagePathInImageStore <String>]
 -ClusterManifestPathInImageStore <String> -ImageStoreConnectionString <String> [-TimeoutSec <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Both
```
Remove-ServiceFabricClusterPackage -CodePackagePathInImageStore <String>
 -ClusterManifestPathInImageStore <String> -ImageStoreConnectionString <String> [-TimeoutSec <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ServiceFabricClusterPackage** cmdlet removes a Service Fabric cluster package from the image store.
Run this cmdlet after you register the package using the Register-ServiceFabricClusterPackage cmdlet.

To manage Service Fabric clusters, start Windows PowerShell by using the **Run as administrator** option.
Before you perform any operation on a Service Fabric cluster, first run the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet to establish a connection to the cluster.

## EXAMPLES

### Example 1: Remove a cluster package
```
PS C:\>Remove-ServiceFabricClusterPackage -ImageStoreConnectionString "xstore:DefaultEndpointsProtocol=https;AccountName=[StorageAccountName];AccountKey=[StorageAccountKey];Container=[ContainerName]" -ClusterManifestPathInImageStore "ClusterManifest_123.xml" -CodePackagePathInImageStore "ServiceFabric.2.0.59.0.msi"
```

This command removes the cluster package that has the specified image store path.
The cmdlet does prompt you for confirmation before it removes the cluster package.

## PARAMETERS

### -ClusterManifestPathInImageStore
Specifies the relative path in the image store of the cluster manifest.
The cmdlet removes the package from the path that this parameter specifies.

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

```yaml
Type: String
Parameter Sets: Config, Both
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Code
Indicates that the cmdlet removes only the Service Fabric .msi file.

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

### -CodePackagePathInImageStore
Specifies the relative path in the image store of the code package.
The cmdlet removes the package from the path that this parameter specifies.

```yaml
Type: String
Parameter Sets: Code, Both
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
Indicates that this cmdlet removes only the Service Fabric cluster manifest.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageStoreConnectionString
Specifies the connection string for the Service Fabric image store.

```yaml
Type: String
Parameter Sets: (All)
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

[Copy-ServiceFabricClusterPackage](./Copy-ServiceFabricClusterPackage.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Register-ServiceFabricClusterPackage](./Register-ServiceFabricClusterPackage.md)
