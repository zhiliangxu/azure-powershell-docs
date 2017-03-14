---
external help file: Microsoft.Open.AzureAD16.Graph.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 01/27/2017 00:01 AM
ms.date: 01/27/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Get-AzureADUserLicenseDetail.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Get-AzureADUserLicenseDetail.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/644983facd286426ad83f709789786ce621938b5
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureADUserLicenseDetail

## SYNOPSIS
Retrieves license details for a user

## SYNTAX

```
Get-AzureADUserLicenseDetail -ObjectId <String>
```

## DESCRIPTION
THis cmdlet retrieves license details for a user

## EXAMPLES

### Example 1
```
PS C:\WINDOWS\system32> Get-AzureADUserLicenseDetail -ObjectId df19e8e6-2ad7-453e-87f5-037f6529ae16

ObjectId                                    ServicePlans
--------                                    ------------
Hv-1hQIEDECePA-ellMl0cjsRfKvdY5Pth8n2BFN5fM {class ServicePlanInfo {...
Hv-1hQIEDECePA-ellMl0QQrjQe98RFBu9S0sbNUzvQ {class ServicePlanInfo {...
```

This example retrieves the license details of the user specified through the ObjectId parameter

## PARAMETERS

### -ObjectId
The object ID of the user for which the license details are retrieved

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

## INPUTS

### System.String


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

