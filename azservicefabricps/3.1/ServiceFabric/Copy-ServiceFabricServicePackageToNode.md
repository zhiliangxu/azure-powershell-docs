---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 156B7382-5026-423F-8570-969F11C4BD5F
updated_at: 11/03/2016 00:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Copy-ServiceFabricServicePackageToNode.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Copy-ServiceFabricServicePackageToNode.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/0fd9fb4ce9179d4ff591e7539b0bcbbb544795ab
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Copy-ServiceFabricServicePackageToNode

## SYNOPSIS
Copies a service package to a target node.

## SYNTAX

```
Copy-ServiceFabricServicePackageToNode [-ServiceManifestName] <String> [-ApplicationTypeName] <String>
 [-ApplicationTypeVersion] <String> [-NodeName] <String> [-PackageSharingPolicies <PackageSharingPolicy[]>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-ServiceFabricServicePackageToNode** cmdlet copies a service package to the Image cache and shared folders on a target node.
You can run this cmdlet to pre-populate nodes with required code, config, and data packages.
Later service creation operations can finish more quickly.

To manage Service Fabric clusters, start Windows PowerShell by using the **Run as administrator** option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](.\Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ApplicationTypeName
Specifies the name for a Service Fabric application type.
The cmdlet copies packages for the application type that this parameter specifies.

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
The cmdlet copies packages for the application type version that this parameter specifies.

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

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet copies the service package to the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageSharingPolicies
Specifies an array of package sharing policies that describe which packages to copy to the shared packages folder on the target node.
To obtain a **PackageSharingPolicy** object, use the **New-ServiceFabricPackageSharingPolicy** cmdlet.

```yaml
Type: PackageSharingPolicy[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceManifestName
Specifies the name of a Service Fabric service package.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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
This cmdlet returns a message that includes the status of the operation.

## NOTES

## RELATED LINKS

[New-ServiceFabricPackageSharingPolicy](./New-ServiceFabricPackageSharingPolicy.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
