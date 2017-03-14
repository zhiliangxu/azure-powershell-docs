---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 9145CA7E-1FF1-44C0-BB40-452161DCB15A
updated_at: 02/22/2017 05:02 AM
ms.date: 02/22/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Register-ServiceFabricApplicationType.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Register-ServiceFabricApplicationType.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/d0829461d8cbb98206f8a4a6aa61aa770784ad21
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Register-ServiceFabricApplicationType

## SYNOPSIS
Registers a Service Fabric application type.

## SYNTAX

```
Register-ServiceFabricApplicationType [-ApplicationPathInImageStore] <String> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Register-ServiceFabricApplicationType** cmdlet registers a Service Fabric application type.

To manage Service Fabric clusters, start Windows PowerShell by using the Run as administrator option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

After you register an application type, you can use the [New-ServiceFabricApplication](./New-ServiceFabricApplication.md) cmdlet to create an application instance, or use the [Start-ServiceFabricApplicationUpgrade](./Start-ServiceFabricApplicationUpgrade.md) cmdlet to upgrade an existing application.

## EXAMPLES

### Example 1: Register an application type
```
PS C:\>Register-ServiceFabricApplicationType -ApplicationPathInImageStore "PersistentToDoListService"
```

This command registers PersistentToDoListService as an application type.

## PARAMETERS

### -ApplicationPathInImageStore
Specifies the relative path of the application type package in the image store.

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

### -Async
The command returns as soon as the registration request has been accepted by the cluster. The [Get-ServiceFabricApplicationType](./Get-ServiceFabricApplicationType.md) command can be used to query the status of the registration request. Using this switch avoids having to provide large -TimeoutSec values when registering large application packages.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
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

[Copy-ServiceFabricApplicationPackage](./Copy-ServiceFabricApplicationPackage.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricApplicationType](./Get-ServiceFabricApplicationType.md)

[Unregister-ServiceFabricApplicationType](./Unregister-ServiceFabricApplicationType.md)

[New-ServiceFabricApplication](./New-ServiceFabricApplication.md)

[Start-ServiceFabricApplicationUpgrade](./Start-ServiceFabricApplicationUpgrade.md)
