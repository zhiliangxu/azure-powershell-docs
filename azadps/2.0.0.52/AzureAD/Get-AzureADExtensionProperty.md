---
external help file: Microsoft.Open.AzureAD16.Graph.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 02/09/2017 07:02 AM
ms.date: 02/09/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Get-AzureADExtensionProperty.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Get-AzureADExtensionProperty.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/1832f8b83a65336d1b6d21bb9072f421b6a5438c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureADExtensionProperty

## SYNOPSIS
Gets  extension properties registered with Azure AD.

## SYNTAX

```
Get-AzureADExtensionProperty [-IsSyncedFromOnPremises <Nullable`1[Boolean]>]
```

## DESCRIPTION
The **Get-AzureADExtensionProperty** cmdlet gets a collection that contains the extension properties registered with Azure Active Directory (Azure AD) through Azure AD Connect. 
You can get extension properties that are synced with on-premises Azure AD, those that are not synced with on-premises Azure AD, or both types. 

## EXAMPLES

### Example 1: Get extension properties synced from on-premises Azure AD 
```
PS C:\> Get-AzureADExtensionProperty -IsSyncedFromOnPremises $True

ObjectId                             Name                                                          TargetObjects
--------                             ----                                                          -------------
b3c7b2c2-bb9a-4e30-a9fc-46adbe8c0899 extension_6e151e1a9cf44f8689a410023ac39235_weather            {User}
05af194f-1068-4539-83c9-06e03a1a1f44 extension_6e151e1a9cf44f8689a410023ac39235_extension_location {User}
9bf6f631-e6a6-41d1-b0a3-777f2acea2d1 extension_ed192e9284d44baf997d1e190a81f28e_extension_4A3UwDDC {User}
```

This command gets extension properties that have been synced from on-premises Azure AD. 

## PARAMETERS

### -IsSyncedFromOnPremises
Specifies whether this cmdlet gets extension properties that are synced or not synced.
- $True. Get extension properties that are synced from the on-premises Azure AD.
- $False. Get extension properties that are not synced from the on-premises Azure AD.
- No value. Get all extension properties.

```yaml
Type: Nullable`1[Boolean]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
