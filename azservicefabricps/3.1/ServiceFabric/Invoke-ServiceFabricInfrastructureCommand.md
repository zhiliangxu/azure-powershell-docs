---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: B61E78F9-61C8-4D0F-897C-1495877A07FB
updated_at: 11/03/2016 08:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricInfrastructureCommand.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricInfrastructureCommand.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/1ee1eb862e0b78a20a656aad5e958efd0f11f85c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Invoke-ServiceFabricInfrastructureCommand

## SYNOPSIS
Invokes an administrative command on an infrastructure service.

## SYNTAX

```
Invoke-ServiceFabricInfrastructureCommand [-Command] <String> [[-ServiceName] <Uri>] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-ServiceFabricInfrastructureCommand** cmdlet invokes an administrative command on an infrastructure service.
The infrastructure service accepts infrastructure-specific commands to allow you to interact directly with the underlying infrastructure by using the Service Fabric API.
To run this cmdlet, at least one instance of the infrastructure service must be enabled in the cluster configuration.
Currently, this cmdlet is supported only on specially-configured Azure Cloud Services.

This cmdlet supports the Service Fabric platform.
Do not run this cmdlet directly.

This cmdlet requires that you connect to the cluster with credentials that are granted administrator access to the cluster.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Command
Specifies the infrastructure-specific command string to send to the infrastructure service.
The format of supported commands depends on the infrastructure on which the cluster runs.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric infrastructure service.
This cmdlet sends the command to the service that this parameter specifies.
The default value is fabric:/System/InfrastructureService.

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

###  
This cmdlet accepts object that contains a **ServiceName** property that identifies the infrastructure service instance to which to send a command.

## OUTPUTS

###  
This cmdlet returns a value that depends on the value of the *Command* parameter, and is determined by the infrastructure.

## NOTES

## RELATED LINKS

[Invoke-ServiceFabricInfrastructureQuery](./Invoke-ServiceFabricInfrastructureQuery.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
