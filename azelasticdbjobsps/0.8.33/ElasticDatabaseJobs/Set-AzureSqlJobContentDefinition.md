---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 9B39643C-534D-47B4-A05F-562BA7088483
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobContentDefinition.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobContentDefinition.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureSqlJobContentDefinition

## SYNOPSIS
Sets the T-SQL script or DACPAC URI definition of content.

## SYNTAX

### Script
```
Set-AzureSqlJobContentDefinition -ContentName <String> -CommandText <String[]> [-Comment <String>]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### Dacpac
```
Set-AzureSqlJobContentDefinition -ContentName <String> -DacpacUri <Uri> [-Comment <String>]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlJobContentDefinition** cmdlet updates the Transact-SQL (T-SQL) script or DACPAC URI definition of content.

## EXAMPLES

### Example 1: Update a T-SQL script definition
```
PS C:\>Set-AzureSqlJobContentDefinition -ContentName "MyScript" -CommandText "SELECT DB_NAME();" -Comment "Updating the script to just select the database name"
CommandText                             ContentName                                                      VersionNumber Comment                               
-----------                             -----------                                                      ------------- -------                               
SELECT DB_NAME();                       MyScript                                                                     2 Updating the script to just select ...
```

This command updates the T-SQL script definition for the specified script content.

## PARAMETERS

### -AzureSqlJobConnection
Specifies the connection state object for the job.
You can get the connection state object through the [New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md) cmdlet.
If you do not specify this parameter, the connection state is used from a prior call to the [Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md) cmdlet.

```yaml
Type: AzureSqlJobConnection
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandText
Specifies the command text of a T-SQL script.
The script can contain GO statements.
When containing GO statements, the system will split the command text into multiple batches.

```yaml
Type: String[]
Parameter Sets: Script
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Comment
Specifies an optional comment describing the change to the content.

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

### -ContentName
Specifies the name of the content.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DacpacUri
Specifies the URI for a DACPAC to be used for application.
The URI must be accessible by the system.

```yaml
Type: Uri
Parameter Sets: Dacpac
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSqlJobContentDefinition](./Get-AzureSqlJobContentDefinition.md)

[New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)
