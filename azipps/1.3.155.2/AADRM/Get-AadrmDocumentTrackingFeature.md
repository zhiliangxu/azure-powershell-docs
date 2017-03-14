---
external help file: Microsoft.RightsManagementServices.Online.Admin.PowerShell.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=623037
schema: 2.0.0
ms.assetid: 3F0BC472-41CC-41CA-A1B5-ACB84B1C2DA9
updated_at: 02/17/2017 00:02 AM
ms.date: 02/17/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Get-AadrmDocumentTrackingFeature.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-aip/blob/master/Azure%20Information%20Protection/AADRM/vlatest/Get-AadrmDocumentTrackingFeature.md
gitcommit: https://github.com/Azure/azure-docs-powershell-aip/blob/572fba461b5027bfccd8712f78d52c7a02e88f01
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AadrmDocumentTrackingFeature

## SYNOPSIS
Indicates whether document tracking is enabled or disabled for Azure Information Protection.

## SYNTAX

```
Get-AadrmDocumentTrackingFeature [<CommonParameters>]
```

## DESCRIPTION
The **Get-AadrmDocumentTrackingFeature** cmdlet indicates whether the Azure Information Protection document tracking feature is enabled or disabled.

You must use PowerShell to get this information about document tracking; you cannot get this information by using a management portal.

For additional information about the document tracking site, see [Configuring and using document tracking for Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-document-tracking) from the Azure Information Protection client administrator guide.

## EXAMPLES

### Example: Determine whether the document tracking site is enabled
```
PS C:\>Get-AadrmDocumentTrackingFeature
```

This command determines whether the Azure Information Protection document tracking feature is enabled.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AadrmDocumentTrackingFeature](./Disable-AadrmDocumentTrackingFeature.md)

[Enable-AadrmDocumentTrackingFeature](./Enable-AadrmDocumentTrackingFeature.md)
