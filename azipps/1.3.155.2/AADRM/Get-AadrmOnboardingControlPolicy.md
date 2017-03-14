---
external help file: Microsoft.RightsManagementServices.Online.Admin.PowerShell.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=521418
schema: 2.0.0
ms.assetid: A5384868-65D1-46A8-A1E0-7050F607131C
updated_at: 02/13/2017 05:02 AM
ms.date: 02/13/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Get-AadrmOnboardingControlPolicy.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Get-AadrmOnboardingControlPolicy.md
gitcommit: https://github.com/Azure/azure-docs-powershell-aip/blob/e4c765ba645ee6c466dd1ff7182695aa9e59fb44
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AadrmOnboardingControlPolicy

## SYNOPSIS
Gets user on-boarding control policy for Rights Management.

## SYNTAX

```
Get-AadrmOnboardingControlPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-AadrmOnboardingControlPolicy** cmdlet obtains your Azure Rights Management user on-boarding control policy to support a gradual deployment by controlling which users in your organization can protect content by using Azure Rights Management.

You must use PowerShell to view this configuration; you cannot view this configuration by using a management portal.

This control can be based on assigned user licenses for the service or membership in a designated security group.
You can also define whether the policy applies to just mobile devices, just Windows clients, or mobile devices and Windows clients. For more information, see [Set-AadrmOnboardingControlPolicy](./Set-AadrmOnboardingControlPolicy.md).

## EXAMPLES

### Example 1: Get the user on-boarding control policy
```
PS C:\> Get-AadrmOnboardingControlPolicy
```

This command displays the user on-boarding control policy for Azure Rights Management for your organization.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AadrmOnboardingControlPolicy](./Set-AadrmOnboardingControlPolicy.md)
