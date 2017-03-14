---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 51657577-F2A0-4D22-822C-3586F0A70B04
updated_at: 02/08/2017 02:02 AM
ms.date: 02/08/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Copy-ServiceFabricApplicationPackage.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Copy-ServiceFabricApplicationPackage.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/b64ab304b822e4fde70815e4d7253d5a15e3311e
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Copy-ServiceFabricApplicationPackage

## SYNOPSIS
Copies a Service Fabric application package to the image store.

## SYNTAX

```
Copy-ServiceFabricApplicationPackage [-ApplicationPackagePath] <String> [-ImageStoreConnectionString] <String>
 [[-ApplicationPackagePathInImageStore] <String>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-ServiceFabricApplicationPackage** cmdlet copies a Service Fabric application package to the image store.

After you copy the application package, use the [Register-ServiceFabricApplicationType](.\Register-ServiceFabricApplicationType.md) cmdlet to register the application type.

To manage Service Fabric clusters, start Windows PowerShell by using the **Run as administrator** option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](.\Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Copy an application package
```
PS C:\> Copy-ServiceFabricApplicationPackage -ApplicationPackagePath "C:\PersistentToDoListService" -ImageStoreConnectionString "xstore:DefaultEndpointsProtocol=https;AccountName=[StorageAccountName];AccountKey=[StorageAccountKey];Container=[ContainerName]"
```

This command copies the application package in the specified path to the image store.

### Example 2: Copy an application package to a specific directory in the image store
```
PS C:\> Copy-ServiceFabricApplicationPackage -ApplicationPackagePath "C:\PersistentToDoListService" -ImageStoreConnectionString "xstore:DefaultEndpointsProtocol=https;AccountName=[StorageAccountName];AccountKey=[StorageAccountKey];Container=[ContainerName]" -ApplicationPackagePathInImageStore "PersistentToDoListService_v2"
```

This command copies the application package in the specified path to the PersistentToDoListService_v2 directory in the image store.

## PARAMETERS

### -ApplicationPackagePath
Specifies the relative path of an application package.
The cmdlet copies the package from the path that you specify.

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

### -ApplicationPackagePathInImageStore
Specifies the relative path in the image store where the application package should be copied to.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSec
Specifies the timeout period in seconds, for the operation.
The maximum timeout value in the image store service is 1800 seconds.

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
This cmdlet returns a message that includes the status of the copy operation.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Register-ServiceFabricApplicationType](./Register-ServiceFabricApplicationType.md)

[Remove-ServiceFabricApplicationPackage](./Remove-ServiceFabricApplicationPackage.md)
