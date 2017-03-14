---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 21624C97-BE06-43D1-944E-C9ECFD1F63E7
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionRestartProgress.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionRestartProgress.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricPartitionRestartProgress

## SYNOPSIS
Gets the progress of a partition restart.

## SYNTAX

```
Get-ServiceFabricPartitionRestartProgress -OperationId <Guid> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricPartitionRestartProgress** cmdlet gets the progress of a partition restart operation in Azure Service Fabric.
Initiate a restart by using the [Start-ServiceFabricPartitionRestart](./Start-ServiceFabricPartitionRestart.md) cmdlet.

## EXAMPLES

### Example 1: Check progress of partition restart operation
```
PS C:\>Get-ServiceFabricPartitionRestartProgress -OperationId ebd322c2-b1d3-46a7-b254-3cc42e6ca2d1
    State ProgressResult
    ----- --------------
Completed SelectedPartition: Service Name: fabric:/ContosoApp/ContosoService, Partition Id: 20a726d0-3112-4c5a-a22c-2e4b8ee8...
```

This command checks the progress of a partition restart operation that has the ID ebd322c2-b1d3-46a7-b254-3cc42e6ca2d1.
The operation is completed.

## PARAMETERS

### -OperationId
Specifies a unique identifier for the operation that this cmdlet checks.
You assign this value when you run **Start-ServiceFabricPartitionRestart**.

```yaml
Type: Guid
Parameter Sets: (All)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-ServiceFabricPartitionRestart](./Start-ServiceFabricPartitionRestart.md)
