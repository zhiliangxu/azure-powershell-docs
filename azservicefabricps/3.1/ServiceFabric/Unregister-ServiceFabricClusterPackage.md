---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 298F2C12-F1BE-4341-B5A0-4C45CF45EB52
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Unregister-ServiceFabricClusterPackage.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Unregister-ServiceFabricClusterPackage.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Unregister-ServiceFabricClusterPackage

## SYNOPSIS
Unregisters a Service Fabric cluster package.

## SYNTAX

### Both (Default)
```
Unregister-ServiceFabricClusterPackage -CodePackageVersion <String> -ClusterManifestVersion <String> [-Force]
 [-TimeoutSec <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Code
```
Unregister-ServiceFabricClusterPackage [-Code] -CodePackageVersion <String> [-ClusterManifestVersion <String>]
 [-Force] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Config
```
Unregister-ServiceFabricClusterPackage [-Config] [-CodePackageVersion <String>]
 -ClusterManifestVersion <String> [-Force] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-ServiceFabricClusterPackage** cmdlet unregisters a Service Fabric cluster package.
If you unregister a cluster package, the cmdlet removes the cluster package from the image store.

To manage Service Fabric clusters, start Windows PowerShell by using the Run as administrator option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Unregister a cluster package
```
PS C:\>Unregister-ServiceFabricClusterPackage -ClusterManifestVersion "V2" -CodePackageVersion "2.0.59.0" -Force
```

This command unregisters the cluster package.
Because the command includes the *Force* parameter, the cmdlet does not prompt you for confirmation.

## PARAMETERS

### -ClusterManifestVersion
Specifies the version stored in a Service Fabric cluster manifest.

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
Indicates that the package includes only a Service Fabric .msi file.

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

### -CodePackageVersion
Specifies the version of the Service Fabric .msi file.

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
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

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Copy-ServiceFabricClusterPackage](./Copy-ServiceFabricClusterPackage.md)

[Register-ServiceFabricClusterPackage](./Register-ServiceFabricClusterPackage.md)
