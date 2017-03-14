---
external help file: Microsoft.Open.AzureAD16.Graph.PowerShell.Custom.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 01/27/2017 00:01 AM
ms.date: 01/27/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Set-AzureADUserThumbnailPhoto.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Set-AzureADUserThumbnailPhoto.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/644983facd286426ad83f709789786ce621938b5
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureADUserThumbnailPhoto

## SYNOPSIS
Set the thumbnail photo for a user

## SYNTAX

### File (Default)
```
Set-AzureADUserThumbnailPhoto [-ObjectId <String>] -FilePath <String>
```

### Stream
```
Set-AzureADUserThumbnailPhoto [-ObjectId <String>] -FileStream <Stream>
```

### ByteArray
```
Set-AzureADUserThumbnailPhoto [-ObjectId <String>] -ImageByteArray <Byte[]>
```

## DESCRIPTION
This cmdlet is used to set the thumbnail photo for a user

## EXAMPLES

### Example 1
```
PS C:\WINDOWS\system32> Set-AzureADUserThumbnailPhoto -ObjectId ba6752c4-6a2e-4be5-a23d-67d8d5980796 -FilePath D:\UserThumbnailPhoto.jpg
```

This example sets the thumbnail photo of the user specified witht eh PObjectId parameter to the image specified with the FilePath parameter

## PARAMETERS

### -FilePath
The file path of the image to be uploaded as the user thumbnail photo

```yaml
Type: String
Parameter Sets: File
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -FileStream
A filestream that contains the user thumbnail photo
```yaml
Type: Stream
Parameter Sets: Stream
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ImageByteArray
An Image Byte Array that contains the user thumbnail photo

```yaml
Type: Byte[]
Parameter Sets: ByteArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ObjectId
The Object ID of the user for which the user thumbnail photo is set

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

## INPUTS

### System.String
System.IO.Stream
System.Byte[]


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

