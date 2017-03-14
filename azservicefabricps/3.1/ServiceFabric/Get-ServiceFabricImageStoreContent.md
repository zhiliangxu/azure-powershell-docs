---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: DD60B18E-5ED7-41B6-B9D4-38BD726DCFF2
updated_at: 11/02/2016 06:11 AM
ms.date: 11/02/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricImageStoreContent.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricImageStoreContent.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/945bc222fc1036fec4385fa64462f3b4fa439079
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricImageStoreContent

## SYNOPSIS
Gets content from the image store.

## SYNTAX

### Application
```
Get-ServiceFabricImageStoreContent [-Application] -ApplicationTypeName <String>
 [-ApplicationTypeVersion <String>] -ImageStoreConnectionString <String> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### Path
```
Get-ServiceFabricImageStoreContent [-Path] [-RemoteRelativePath <String>] -ImageStoreConnectionString <String>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricImageStoreContent** cmdlet gets content from the Service Fabric image store.

## EXAMPLES

### Example 1: Get image store content by application name/type
```
PS C:\>Get-ServiceFabricImageStoreContent -Application -ApplicationTypeName "CalcServiceApp" -ApplicationTypeVersion "2.0" -ImageStoreConnectionString "fabric:ImageStore"
```

This command gets image store content that belongs to the application CalcServiceApp, type version 2.0.

### Example 2: Get image store content by relative path
```
PS C:\>Get-ServiceFabricImageStoreContent -Path -RemoteRelativePath "Store\CalcServiceApp\apps" -ImageStoreConnectionString "fabric:ImageStore"
```

This command gets image store content for all application instances.

## PARAMETERS

### -Application
Indicates that image store content is searched by application type name and version.

```yaml
Type: SwitchParameter
Parameter Sets: Application
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeName
Specifies the name of a Service Fabric application type.

```yaml
Type: String
Parameter Sets: Application
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeVersion
Specifies the version of a Service Fabric application type version.

```yaml
Type: String
Parameter Sets: Application
Aliases: 

Required: False
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Indicates that image store content is searched by using the image store relative path.

```yaml
Type: SwitchParameter
Parameter Sets: Path
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteRelativePath
Specifies the relative path to the image store root.

```yaml
Type: String
Parameter Sets: Path
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

###  
**Get-ServiceFabricStoreContent** accepts string instances of a Service Fabric application type; the version of an application type; or the image store relative path.

## OUTPUTS

###  
**Get-ServiceFabricStoreContent** returns instances of the  **System.Fabric.Management.ImageStore.ImageStoreFile** object and/or the **System.Fabric.Management.ImageStore.ImageStoreFolder** object.

## NOTES

## RELATED LINKS


