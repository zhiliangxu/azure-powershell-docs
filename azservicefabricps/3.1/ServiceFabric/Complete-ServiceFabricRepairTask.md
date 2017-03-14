---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: FF0A85E2-0CAB-4762-B813-47C420DF9FB8
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Complete-ServiceFabricRepairTask.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Complete-ServiceFabricRepairTask.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Complete-ServiceFabricRepairTask

## SYNOPSIS
Reports that a manual repair task is finished.

## SYNTAX

```
Complete-ServiceFabricRepairTask [-TaskId] <String> [[-Version] <Int64>] [-ResultStatus <RepairTaskResult>]
 [-ResultCode <Int32>] [-ResultDetails <String>] [-Force] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Complete-ServiceFabricRepairTask** cmdlet reports that a manual Service Fabric repair task is finished.
After you run this cmdlet, the repair task is no longer approved to be run.
No additional repair work is started on the entities described by the repair task.
If you are unsure of the status of the repair work, do not report completion of the repair task.
Performing repair work after you run this cmdlet can result in availability or data loss.
If subsequent repairs are needed, start a new repair task and wait for approval of that repair task.

This cmdlet supports the Service Fabric platform.
Do not run this cmdlet directly.

This cmdlet requires that you connect to the cluster with credentials that are granted administrator access to the cluster.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](.\Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Complete a manual repair task successfully
```
PS C:\>Complete-ServiceFabricRepairTask -TaskId MyRepairTaskID
```

This command marks the manual repair task that has the ID MyRepairTaskId as completed successfully.

### Example 2: Complete a manual repair task with details
```
PS C:\>Complete-ServiceFabricRepairTask -TaskId MyRepairTaskID -ResultStatus Cancelled -ResultCode 42 -ResultDetails "Repair was no longer needed"
```

This command marks the manual repair task that has the ID MyRepairTaskId as cancelled and includes additional details.

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
Forces the command to run even if the specified repair task does not appear to be a manual repair task.

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

### -ResultCode
Specifies a value that provides additional details about the result of the repair task.

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

### -ResultDetails
Specifies a string that provide additional details about the result of the repair task.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultStatus
Specifies a value that describes the overall result of the repair task.
Valid values are:

- Invalid.
Do not specify this value.
- Succeeded.
The repair task succeeded.
- Cancelled.
The repair task was cancelled.
- Interrupted.
The repair task was interrupted.
- Failed.
The repair task failed.
- Pending.
Do not specify this value.

```yaml
Type: RepairTaskResult
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, Succeeded, Cancelled, Interrupted, Failed, Pending

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskId
Specifies the ID of the repair task to complete.

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
This cmdlet accepts the repair task to complete.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Approve-ServiceFabricRepairTask](./Approve-ServiceFabricRepairTask.md)

[Get-ServiceFabricRepairTask](./Get-ServiceFabricRepairTask.md)

[Remove-ServiceFabricRepairTask](./Remove-ServiceFabricRepairTask.md)

[Start-ServiceFabricRepairTask](./Start-ServiceFabricRepairTask.md)

[Stop-ServiceFabricRepairTask](./Stop-ServiceFabricRepairTask.md)
