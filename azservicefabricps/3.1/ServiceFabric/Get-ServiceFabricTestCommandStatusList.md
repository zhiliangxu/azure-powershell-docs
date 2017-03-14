---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 26459CBC-9296-4B65-A298-E6B31EF65865
updated_at: 11/03/2016 08:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricTestCommandStatusList.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricTestCommandStatusList.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/1ee1eb862e0b78a20a656aad5e958efd0f11f85c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricTestCommandStatusList

## SYNOPSIS
Gets test commands.

## SYNTAX

```
Get-ServiceFabricTestCommandStatusList [-StateFilter <TestCommandStateFilter>]
 [-TypeFilter <TestCommandTypeFilter>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricTestCommandStatusList** cmdlet gets test commands in Azure Service Fabric.
To run this cmdlet, **FaultAnalysisService** must be enabled.

## EXAMPLES

### Example 1: Get status of cancelled test commands
```
PS C:\>Get-ServiceFabricTestCommandStatusList -StateFilter Cancelled
OperationId                              State     TestCommandType
-----------                              -----     ---------------
a268cc73-2e30-462b-b3df-3a0d30e5b330 Cancelled PartitionQuorumLoss
```

This command gets the status of test commands that have been cancelled.
In this example, the command finds one command.

### Example 2: Get status of all test commands
```
PS C:\>Get-ServiceFabricTestCommandStatusList
OperationId                              State     TestCommandType
-----------                              -----     ---------------
aeaceca9-320d-4f7b-84e8-3cc13c29a974 Completed PartitionQuorumLoss
0e3fa169-dec0-46d1-8eff-2f1a4a3f5fde Completed    PartitionRestart
a268cc73-2e30-462b-b3df-3a0d30e5b330 Cancelled PartitionQuorumLoss
51ed168c-bb22-47d5-97f9-6b74b353bb33 Completed PartitionQuorumLoss
ebd322c2-b1d3-46a7-b254-3cc42e6ca2d1 Completed    PartitionRestart
d3f12b09-6a90-4745-a4fc-3f92149a7419 Completed   PartitionDataLoss
```

This command gets the status of all test commands.
The returned list contains five completed test commands, and one cancelled test command.

## PARAMETERS

### -StateFilter
Specifies the state of commands that this cmdlet gets.
The acceptable values for this parameter are:

- Default
- Running
- RollingBack
- CompletedSuccessfully
- Failed
- Cancelled
- ForceCancelled
- All

```yaml
Type: TestCommandStateFilter
Parameter Sets: (All)
Aliases:
Accepted values: Default, Running, RollingBack, CompletedSuccessfully, Failed, Cancelled, ForceCancelled, All

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

### -TypeFilter
Specifies the type of commands that this cmdlet gets.
The acceptable values for this parameter are:

- PartitionDataLoss
- PartitionQuorumLoss
- PartitionRestart

```yaml
Type: TestCommandTypeFilter
Parameter Sets: (All)
Aliases:
Accepted values: Default, PartitionDataLoss, PartitionQuorumLoss, PartitionRestart, All

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

[Stop-ServiceFabricTestCommand](./Stop-ServiceFabricTestCommand.md)
