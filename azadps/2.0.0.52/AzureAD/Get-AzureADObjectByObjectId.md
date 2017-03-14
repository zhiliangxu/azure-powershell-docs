---
external help file: Microsoft.Open.AzureAD16.Graph.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 01/27/2017 00:01 AM
ms.date: 01/27/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Get-AzureADObjectByObjectId.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Get-AzureADObjectByObjectId.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/644983facd286426ad83f709789786ce621938b5
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureADObjectByObjectId

## SYNOPSIS
Retrieves the object(s) specified by the objectIds parameter 

## SYNTAX

```
Get-AzureADObjectByObjectId -ObjectIds <System.Collections.Generic.List`1[System.String]>
 [-Types <System.Collections.Generic.List`1[System.String]>]
```

## DESCRIPTION
Retrieves the object(s) specified by the objectIds parameter

## EXAMPLES

### Example 1
```
PS C:\WINDOWS\system32> Get-AzureADObjectByObjectId -ObjectIds 2af3478a-27da-4837-a387-b22b3fb236a8, c4fdf87f-f68e-4859-8bcf-36579b66005e

ObjectId                             AppId                                DisplayName
--------                             -----                                -----------
c4fdf87f-f68e-4859-8bcf-36579b66005e 71715b24-8cdd-432b-a138-86e8ad179274 Woodgrove HR App

DeletionTimeStamp                   :
ObjectId                            : 2af3478a-27da-4837-a387-b22b3fb236a8
ObjectType                          : DeviceConfiguration
PublicIssuerCertificates            : {}
CloudPublicIssuerCertificates       : {}
RegistrationQuota                   : 20
MaximumRegistrationInactivityPeriod : 90
```

In this example two objects are retrieved (a DeviceConfiguration object and an Application object) as specified by the value of the ObjectIds parameter

## PARAMETERS

### -ObjectIds
One or more object ID's, separated by commas, for which the objects are retrieved

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Types
Specifies the type of objects that the cmdlet returns

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

