---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 44A9AA7C-9D72-4B62-B53E-9A773EA1EED5
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricPackageSharingPolicy.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricPackageSharingPolicy.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-ServiceFabricPackageSharingPolicy

## SYNOPSIS
Creates a package sharing policy.

## SYNTAX

### All
```
New-ServiceFabricPackageSharingPolicy [[-PackageName] <String>] [-SharingScopeAll] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### Code
```
New-ServiceFabricPackageSharingPolicy [[-PackageName] <String>] [-SharingScopeCode] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### Config
```
New-ServiceFabricPackageSharingPolicy [[-PackageName] <String>] [-SharingScopeConfig] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### Data
```
New-ServiceFabricPackageSharingPolicy [[-PackageName] <String>] [-SharingScopeData] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-ServiceFabricPackageSharingPolicy** cmdlet creates a package sharing policy.
You can pass a **PackageSharingPolicy** object to the [Copy-ServiceFabricServicePackageToNode](.\Copy-ServiceFabricServicePackageToNode.md) cmdlet.

To manage Service Fabric clusters, start Windows PowerShell by using the Run as administrator option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Copy-ServiceFabricServicePackageToNode](./Copy-ServiceFabricServicePackageToNode.md) cmdlet.

## EXAMPLES

## PARAMETERS

### -PackageName
Specifies the name of the package that to share.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharingScopeAll
Indicates that this cmdlet uses **All** as the package sharing scope.
The **All** scope shares all code, config, and data packages from the service manifest.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharingScopeCode
Indicates that this cmdlet uses **Code** as the package sharing scope.
The **Code** scope shares all code packages from the service manifest.

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

### -SharingScopeConfig
Indicates that this cmdlet uses **Config** as the package sharing scope.
The **Config** scope shares all config packages from the service manifest.

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

### -SharingScopeData
Indicates that this cmdlet uses **Data** as the package sharing scope.
The **Data** scope shares all data packages from the service manifest.

```yaml
Type: SwitchParameter
Parameter Sets: Data
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
This cmdlet returns a **System.Fabric.PackageSharingPolicy** object for a Service Fabric package.

## NOTES

## RELATED LINKS

[Copy-ServiceFabricServicePackageToNode](./Copy-ServiceFabricServicePackageToNode.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
