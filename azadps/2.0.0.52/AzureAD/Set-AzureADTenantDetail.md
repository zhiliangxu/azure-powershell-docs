---
external help file: Microsoft.Open.AzureAD16.Graph.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 01/27/2017 00:01 AM
ms.date: 01/27/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Set-AzureADTenantDetail.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Set-AzureADTenantDetail.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/644983facd286426ad83f709789786ce621938b5
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureADTenantDetail

## SYNOPSIS
Set contact details for a tenant

## SYNTAX

```
Set-AzureADTenantDetail [-MarketingNotificationEmails <System.Collections.Generic.List`1[System.String]>]
 [-SecurityComplianceNotificationMails <System.Collections.Generic.List`1[System.String]>]
 [-SecurityComplianceNotificationPhones <System.Collections.Generic.List`1[System.String]>]
 [-TechnicalNotificationMails <System.Collections.Generic.List`1[System.String]>]
```

## DESCRIPTION
This cmdlet is used to set various contact details for a tenant.

## EXAMPLES

### Example 1
```
PS C:\WINDOWS\system32> Set-AzureADTenantDetail -MarketingNotificationEmails "amy@contoso.com","henry@contoso.com" -SecurityComplianceNotificationMails "john@contoso.com","mary@contoso.com" -SecurityComplianceNotificationPhones "1-555-625-9999", "1-555-233-5544" -TechnicalNotificationMails "peter@contoso.com"
```

THis example shows how to set the various tenant details

## PARAMETERS

### -MarketingNotificationEmails
The email address that is used to send marketing notification emails

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityComplianceNotificationMails
The email address that is used to send security compliance emails

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityComplianceNotificationPhones
The phone number(s) that are used for security compliance 

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TechnicalNotificationMails
The email addres(es) that are used for technical notification emails

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

