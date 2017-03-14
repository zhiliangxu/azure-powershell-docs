---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: EF6C08E7-6811-4F74-84FB-D4FCE4D6FAFD
updated_at: 11/23/2016 04:11 AM
ms.date: 11/23/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Approve-ServiceFabricRepairTask.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Approve-ServiceFabricRepairTask.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/2a5ea82fb26724d20409558b5656bffc61dfe3b3
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Approve-ServiceFabricRepairTask

## SYNOPSIS
Forces approval of a repair task.

## SYNTAX

```
Approve-ServiceFabricRepairTask [-TaskId] <String> [[-Version] <Int64>] [-Force] [-TimeoutSec <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Approve-ServiceFabricRepairTask** cmdlet forces the approval of a Service Fabric repair task that is in the preparing state.
Because this cmdlet bypasses safety checks, it may result in availability or data loss.
Evaluate the potential impact of this operation before you use this cmdlet.

This cmdlet supports the Service Fabric platform.
Do not run this cmdlet directly.

If you approve a repair task by force, then the **ForcedApproval** flag will be set on that task.

This cmdlet requires that you connect to the cluster with credentials that are granted administrator access to the cluster.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](.\Connect-ServiceFabricCluster) cmdlet.

## EXAMPLES

### Example 1: Approve a repair task
```
PS C:\>Approve-ServiceFabricRepairTask -TaskId "MyRepairTaskID"
```

This command approves the repair task that has the ID MyRepairTaskId.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskId
Specifies the ID of the repair task to approve.

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

### -Version
Specifies the current version of the repair task.
The request can succeed only if the value that this parameter specifies matches the current value of the repair task.
Specify a value of zero (0) to skip version check.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Fabric.Repair.RepairTask
This command accepts a repair task to approve.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Complete-ServiceFabricRepairTask](./Complete-ServiceFabricRepairTask.md)

[Get-ServiceFabricRepairTask](./Get-ServiceFabricRepairTask.md)

[Remove-ServiceFabricRepairTask](./Remove-ServiceFabricRepairTask.md)

[Start-ServiceFabricRepairTask](./Start-ServiceFabricRepairTask.md)

[Stop-ServiceFabricRepairTask](./Stop-ServiceFabricRepairTask.md)
