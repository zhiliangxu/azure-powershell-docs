---
external help file: Microsoft.RightsManagementServices.Online.Admin.PowerShell.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=400619
schema: 2.0.0
ms.assetid: A3A194BD-D7B2-417F-902D-33D40BB3B332
updated_at: 02/13/2017 05:02 AM
ms.date: 02/13/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Get-AadrmUsageLogStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Get-AadrmUsageLogStorageAccount.md
gitcommit: https://github.com/Azure/azure-docs-powershell-aip/blob/e4c765ba645ee6c466dd1ff7182695aa9e59fb44
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AadrmUsageLogStorageAccount

## SYNOPSIS
Gets the location for usage logs.

## SYNTAX

```
Get-AadrmUsageLogStorageAccount [<CommonParameters>]
```

## DESCRIPTION
The **Get-AadrmUsageLogStorageAccount** cmdlet gets the Azure storage location for usage logs for Azure Rights Management.

You must use PowerShell to get this information; you cannot do this action by using a management portal.

This cmdlet should be used only if you have usage logs prior to the usage logging change in February 2016.
After this date, the only Windows PowerShell cmdlet that you need for Azure RMS usage logging is the [Get-AadrmUserLog](./Get-AadrmUserLog.md) cmdlet.

For more information about usage logging, see [Logging and analyzing Azure Rights Management usage](https://docs.microsoft.com/rights-management/deploy-use/log-analyze-usage) (https://docs.microsoft.com/rights-management/deploy-use/log-analyze-usage) on the Microsoft documentation site.

## EXAMPLES

### Example 1: Get the log location
```
PS C:\>Get-AadrmUsageLogStorageAccount
```

This command gets the location for your usage logs.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AadrmUserLog](./Get-AadrmUserLog.md)

[Set-AadrmUsageLogStorageAccount](./Set-AadrmUsageLogStorageAccount.md)

[Logging and analyzing Azure Rights Management usage](https://docs.microsoft.com/rights-management/deploy-use/log-analyze-usage)
