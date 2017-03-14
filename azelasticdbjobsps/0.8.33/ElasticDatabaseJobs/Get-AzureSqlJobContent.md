---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 59C3B502-9CBE-4F84-88AE-7954B486A0DD
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobContent.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobContent.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJobContent

## SYNOPSIS
Gets content containers to run or apply across entities in a target.

## SYNTAX

### All (Default)
```
Get-AzureSqlJobContent [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### ContentName
```
Get-AzureSqlJobContent -ContentName <String[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJobContent** cmdlet gets one or multiple content containers that can be run or applied across entities within a job target.

Content contains one or multiple versioned definitions.
You can get versioned definitions by using the [Get-AzureSqlJobContentDefinition](./Get-AzureSqlJobContentDefinition.md) cmdlet.

## EXAMPLES

### Example 1: Get all content defined in the system
```
PS C:\>Get-AzureSqlJobContent
ContentName                                                        ContentType
-----------                                                        -----------
MyDacpac                                                           Dacpac
MyScript                                                           Script
CreateMyTestTable                                                  Script
```

This command gets all content defined within the system.

### Example 2: Get content for a specified name
```
PS C:\>Get-AzureSqlJobContent -ContentName "MyScript"
ContentName                                                        ContentType
-----------                                                        -----------
MyScript                                                           Script
```

This command gets content for the specified name.

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

### -ContentName
Specifies an array that contains the content.

```yaml
Type: String[]
Parameter Sets: ContentName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureSqlJobContent](./New-AzureSqlJobContent.md)

[Get-AzureSqlJobContentDefinition](./Get-AzureSqlJobContentDefinition.md)

[Set-AzureSqlJobContentDefinition](./Set-AzureSqlJobContentDefinition.md)

[New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
