---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 0F403FD1-EA91-4040-BD9E-D289B59F0E01
updated_at: 11/12/2016 06:11 AM
ms.date: 11/12/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Test-ServiceFabricService.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Test-ServiceFabricService.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a3759ddf1f1f1ba503e1480f257a7293a1f4c23a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Test-ServiceFabricService

## SYNOPSIS
Validates a Service Fabric service.

## SYNTAX

```
Test-ServiceFabricService [-ServiceName] <Uri> [-MaxStabilizationTimeoutSec] <Int32> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-ServiceFabricService** cmdlet validates the availability and health of all Service Fabric services within an application.
This cmdlet verifies that the services are at the target replica set size and that the services are healthy.
This cmdlet also validates that there are no InBuild replicas.
Use this cmdlet to verify that your service is stable after inducing any fault into the system.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Test a service
```
PS C:\>Test-ServiceFabricService -ServiceName fabric:/SvcName -MaxStabilizationTimeoutSec 240
```

This command tests the specified service to make sure that it is stable within 240 seconds.

## PARAMETERS

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

### -ServiceName
Specifies the name of the service to test.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Uri
Represents the name of a Service Fabric service.

## OUTPUTS

### System.Object
This cmdlet returns a **String** object that represents the status of validation.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricService](./Get-ServiceFabricService.md)

[New-ServiceFabricService](./New-ServiceFabricService.md)

[Remove-ServiceFabricService](./Remove-ServiceFabricService.md)

[Test-ServiceFabricService](./Test-ServiceFabricService.md)

[Update-ServiceFabricService](./Update-ServiceFabricService.md)
