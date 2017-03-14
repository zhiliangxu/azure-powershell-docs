---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 004C9EF9-80DE-4B23-AD63-652B7F4FF1A4
updated_at: 03/08/2017 14:03 PM
ms.date: 03/08/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionDataLossProgress.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionDataLossProgress.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/9f64faa62bfa9d7f879864db4a9a59233d0c37db
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricPartitionDataLossProgress

## SYNOPSIS

Gets the progress of a data loss fault operation.

## SYNTAX

```
Get-ServiceFabricPartitionDataLossProgress -OperationId <Guid> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricPartitionDataLossProgress** cmdlet gets the progress of a data loss fault operation in Azure Service Fabric.
Initiate a data loss fault operation using the [Start-ServiceFabricPartitionDataLoss](./Start-ServiceFabricPartitionDataLoss.md) cmdlet.

## EXAMPLES

### Example 1: Check progress of data loss fault operation

```
PS C:\>Get-ServiceFabricPartitionDataLossProgress -OperationId d3f12b09-6a90-4745-a4fc-3f92149a7419
    State ProgressResult
    ----- --------------
Completed SelectedPartition: Service Name: fabric:/ContosoApp/PersistServ, Partition Id: 67e2c139-ccf0-4562-9f2b-bf35e4c2...
```

This command checks the progress of a data loss fault operation that has the ID d3f12b09-6a90-4745-a4fc-3f92149a7419. The **State** of the fault operation is **Completed**.

## PARAMETERS

### -OperationId

Specifies a unique identifier for the fault operation that this cmdlet checks.
You assign this value when you run [Start-ServiceFabricPartitionDataLoss](./Start-ServiceFabricPartitionDataLoss.md).

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

## RELATED LINKS

[Start-ServiceFabricPartitionDataLoss](./Start-ServiceFabricPartitionDataLoss.md)
