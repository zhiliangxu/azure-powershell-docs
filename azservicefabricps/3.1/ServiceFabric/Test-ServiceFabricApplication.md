---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 1E932261-A36C-46A2-A1C7-D656A10E8F66
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Test-ServiceFabricApplication.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Test-ServiceFabricApplication.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Test-ServiceFabricApplication

## SYNOPSIS
Validates a Service Fabric application.

## SYNTAX

```
Test-ServiceFabricApplication [-ApplicationName] <Uri> [-MaxStabilizationTimeoutSec] <Int32>
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-ServiceFabricApplication** cmdlet tests the availability and health of a Service Fabric application.
This cmdlet verifies that the service is at the target replica set size and that the service health is good.
This cmdlet also validates that there are no InBuild replicas.
Use this cmdlet to verify that your service is stable after inducing any fault into the system.

Before using this cmdlet, connect to the Service Fabric cluster.

## EXAMPLES

### Example 1: Validate an application
```
PS C:\>Test-ServiceFabricApplication -ApplicationName fabric:/AppName -MaxStabilizationTimeoutSec 240
```

This command tests all of the services in the specified application to make sure that they are stable within 240 seconds.

## PARAMETERS

### -ApplicationName
Specifies the name of the application to test.

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

### -MaxStabilizationTimeoutSec
Specifies the maximum time-out period, in seconds, for the cluster to stabilize before failing the test.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### System.Uri
Represents the name of a Service Fabric service.

## OUTPUTS

### System.Object
This cmdlet returns a **String** object that represents the status of the validation.

## NOTES

## RELATED LINKS

[Get-ServiceFabricApplication](./Get-ServiceFabricApplication.md)

[New-ServiceFabricApplication](./New-ServiceFabricApplication.md)

[Remove-ServiceFabricApplication](./Remove-ServiceFabricApplication.md)

[Update-ServiceFabricApplication](./Update-ServiceFabricApplication.md)
