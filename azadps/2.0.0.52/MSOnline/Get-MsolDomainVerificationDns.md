---
external help file: Microsoft.Online.Administration.Automation.PSModule.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 20D3AFFB-C7B5-40C4-8379-CE115EC668FC
updated_at: 11/10/2016 02:11 AM
ms.date: 11/10/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Get-MsolDomainVerificationDns.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Get-MsolDomainVerificationDns.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/7986fb4880d0ee292c289166871e4b25df1ad4b8
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-MsolDomainVerificationDns

## SYNOPSIS
Gets DNS records necessary to verify a domain.

## SYNTAX

```
Get-MsolDomainVerificationDns -DomainName <String> [-Mode <DomainVerificationMode>] [-TenantId <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsolDomainVerificationDns** cmdlet gets the DNS records that need to be set to verify a domain.

## EXAMPLES

### Example 1: Get DNS records that need to be set verify ownership of a domain
```
PS C:\> Get-MsolDomainVerificationDNS -DomainName "contoso.com"
```

This command gets the DNS records that need to be set in order to verify ownership of contoso.com.

## PARAMETERS

### -DomainName
Specifies the fully qualified domain name to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Mode
Specifies the domain verification mode to use when verifying this domain.
Valid values are: DnsMXRecord and DnsTxtRecord.

```yaml
Type: DomainVerificationMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantId
Specifies the unique ID of the tenant on which to perform the operation.
The default value is the tenant of the current user.
This parameter applies only to partner users.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Online.Administration.DomainRecord
This cmdlet returns details about the DNS records required to verify a domain.

## NOTES

## RELATED LINKS
