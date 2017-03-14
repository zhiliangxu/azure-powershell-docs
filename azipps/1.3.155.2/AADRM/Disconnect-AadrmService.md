---
external help file: Microsoft.RightsManagementServices.Online.Admin.PowerShell.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=400601
schema: 2.0.0
ms.assetid: 91DD14FF-0033-4A7F-9738-87BD2A989FED
updated_at: 02/09/2017 02:02 AM
ms.date: 02/09/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Disconnect-AadrmService.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Disconnect-AadrmService.md
gitcommit: https://github.com/Azure/azure-docs-powershell-aip/blob/b5b814c02caa6cd576a3db614749957f10782144
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Disconnect-AadrmService

## SYNOPSIS
Disconnects from Rights Management.

## SYNTAX

```
Disconnect-AadrmService [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-AadrmService** cmdlet disconnects you from the Azure Rights Management service. Use this cmdlet to end a connection that you previously established by using the [Connect-AadrmService](./Connect-AadrmService.md) cmdlet.

## EXAMPLES

### Example 1: Disconnect from Rights Management
```
PS C:\>Disconnect-AadrmService
```

This command disconnects from the Rights Management service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Connect-AadrmService](./Connect-AadrmService.md)
