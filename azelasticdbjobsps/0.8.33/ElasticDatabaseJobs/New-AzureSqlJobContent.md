---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: FCAA0791-9557-4CDE-A2D5-AE9B174003ED
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobContent.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobContent.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-AzureSqlJobContent

## SYNOPSIS
Creates content that can be run or applied across entities within a job target.

## SYNTAX

### Script
```
New-AzureSqlJobContent -ContentName <String> -CommandText <String[]>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### Dacpac
```
New-AzureSqlJobContent -ContentName <String> -DacpacUri <Uri>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlJobContent** cmdlet creates content that can be run or applied across entities within a job target.
Content can be created in the form of T-SQL scripts or DACPAC URIs.

## EXAMPLES

### Example 1: Create a T-SQL script to be used for execution
```
PS C:\>New-AzureSqlJobContent -ContentName "CreateMyTestTable" -CommandText "IF NOT EXISTS (SELECT name FROM SYS.TABLES WHERE name = 'MyTestTable') BEGIN CREATE TABLE MyTestTable(X INT PRIMARY KEY IDENTITY, Y INT) END"
ContentName                                                                                                 ContentType
-----------                                                                                                 -----------
CreateMyTestTable                                                                                                Script
```

This command creates a T-SQL script to be used for execution within a job.

### Example 2: Import a T-SQL script from a file to be used for execution
```
PS C:\>New-AzureSqlJobContent -ContentName "MyScript" -CommandText (Get-Content .\MyScript.sql)
ContentName                                                                                                 ContentType
-----------                                                                                                 -----------
MyScript                                                                                                         Script
```

This command imports a T-SQL script from a file to be used for execution within a job.

### Example 3: Create DACPAC content to be used for execution within a job
```
PS C:\>New-AzureSqlJobContent -ContentName "MyDacpac" -DacpacUri "http://mystorageaccount.blob.core.windows.net/myContainer/mydacpac.dacpac?sv=2014-02-14&amp;sr=c&amp;sig=7q%2FpZvcD2ivMgiqZ2qwNF6GBI8XLPmAz3%2B4hfbtQf4k%3D&amp;st=2015-06-12T07%3A00%3A00Z&amp;se=2099-06-20T07%3A00%3A00Z&amp;sp=r"
ContentName                                                                                                 ContentType
-----------                                                                                                 -----------
MyDacpac                                                                                                         Dacpac
```

This command creates DACPAC content to be used for execution within a job.
The provided URI should be publically accessible to allow the system to successfully apply the DACPAC across the job target.

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
When containing GO statements, the system splits the command text into multiple batches.

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

[Get-AzureSqlJobContent](./Get-AzureSqlJobContent.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
