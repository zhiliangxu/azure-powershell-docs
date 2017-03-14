---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 4275CC75-BDDD-4782-99C8-D3E775F07E61
updated_at: 03/07/2017 08:03 AM
ms.date: 03/07/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricService.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricService.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/82e054d9eb8245c34714466bf9638dbff608d9f0
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricService

## SYNOPSIS
Gets a list of Service Fabric services.

## SYNTAX

### Non-Adhoc (Default)
```
Get-ServiceFabricService [-ApplicationName] <Uri> [[-ServiceName] <Uri>] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

### Adhoc
```
Get-ServiceFabricService [-Adhoc] [[-ServiceName] <Uri>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricService** cmdlet gets a list of Service Fabric services.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the services created from an application
```
PS C:\>Get-ServiceFabricService -ApplicationName fabric:/myapp/persistenttodolist
```

This command gets the Service Fabric services from the specified application.

### Example 2: Get the system services running in a cluster
```
PS C:\>Get-ServiceFabricService -ApplicationName fabric:/System
```

This command gets the Service Fabric system services running in a cluster.

## PARAMETERS

### -Adhoc
Indicates that the service runs in ad hoc mode.
In ad hoc mode, you manually activate the service host.

```yaml
Type: SwitchParameter
Parameter Sets: Adhoc
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet gets the services for the applications that you specify.

```yaml
Type: Uri
Parameter Sets: Non-Adhoc
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the URI of a Service Fabric service.
If you do not specify this parameter, this cmdlet gets all services of the specified application.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### System.Uri
This cmdlet accept a URI that represents the name of a Service Fabric application or the name of a Service Fabric service.

## OUTPUTS

### System.Object
This cmdlet returns a list of **[System.Fabric.Query.Service](https://docs.microsoft.com/en-us/dotnet/api/system.fabric.query.service)** objects that represent Service Fabric services.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[New-ServiceFabricService](./New-ServiceFabricService.md)

[Remove-ServiceFabricService](./Remove-ServiceFabricService.md)

[Resolve-ServiceFabricService](./Resolve-ServiceFabricService.md)

[Update-ServiceFabricService](./Update-ServiceFabricService.md)
