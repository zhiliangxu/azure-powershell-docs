---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 03/07/2017 02:03 AM
ms.date: 03/07/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricApplicationName.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricApplicationName.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/4cb24501dd16bc0b7a49d0f7aef9167facbddba0
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricApplicationName

## SYNOPSIS
Gets the Service Fabric Application name from the Service Fabric Service name.

## SYNTAX

```
Get-ServiceFabricApplicationName [-ServiceName] <Uri> [-TimeoutSec <Int32>]
```

## DESCRIPTION
The **Get-ServiceFabricApplicationName** cmdlet gets the name of the application for a Service Fabric service.

The output of **Get-ServiceFabricApplicationName** contains the following information:

--Application Name: The name of the application corresponding to the given service.

## EXAMPLES

### Example 1
```
PS C:\> Get-ServiceFabricApplicationName -ServiceName  fabric:/myapp/persistenttodolist
```

The command above gets the application name for the service fabric:/myapp/persistenttodolist

## PARAMETERS

### -ServiceName
Specifies a Service Fabric service.

```yaml
Type: Uri
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Uri
This cmdlet accepts a string that represents the service name.

## OUTPUTS

### System.Object
This cmdlet returns an [ApplicationNameResult](https://docs.microsoft.com/dotnet/api/system.fabric.query.applicationnameresult) that contains the Application name.

## NOTES

## RELATED LINKS

[Get-ServiceFabricServiceName](./Get-ServiceFabricServiceName.md)
