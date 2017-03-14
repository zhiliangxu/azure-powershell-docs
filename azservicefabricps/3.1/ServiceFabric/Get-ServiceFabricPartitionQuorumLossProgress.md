---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: A3614BE3-5C8A-419D-BAD4-01B1443248A9
updated_at: 03/08/2017 14:03 PM
ms.date: 03/08/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionQuorumLossProgress.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionQuorumLossProgress.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/56c158512a4de98aa6e95e18779fedb1b5012b55
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricPartitionQuorumLossProgress

## SYNOPSIS

Gets the progress of a quorum loss fault operation.

## SYNTAX

```
Get-ServiceFabricPartitionQuorumLossProgress -OperationId <Guid> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION

The **Get-ServiceFabricPartitionQuorumLossProgress** cmdlet gets the progress of a quorum loss fault operation. Initiate a quorum loss fault by using the [Start-ServiceFabricPartitionQuorumLoss](./Start-ServiceFabricPartitionQuorumLoss.md) cmdlet.

## EXAMPLES

### Example 1: Check progress of quorum loss fault operation
```
PS C:\>Get-ServiceFabricPartitionQuorumLossProgress -OperationId aeaceca9-320d-4f7b-84e8-3cc13c29a974
  State Result
  ----- ------
Running
```

This command checks the progress of a quorum loss fault operation that has the ID aeaceca9-320d-4f7b-84e8-3cc13c29a974.
The **State** of the fault operation is still **Running** and that is why the **Result** is empty.

## PARAMETERS

### -OperationId

Specifies a unique identifier for the fault operation that this cmdlet checks.
You assign this value when you run **Start-ServiceFabricPartitionQuorumLoss**.

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

[Start-ServiceFabricPartitionQuorumLoss](./Start-ServiceFabricPartitionQuorumLoss.md)
