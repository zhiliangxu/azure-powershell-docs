---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: CC57C3D8-784E-4885-A65D-CA59EFF78E35
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobContentDefinition.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobContentDefinition.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJobContentDefinition

## SYNOPSIS
Gets one or multiple content definitions that are run or applied across entities within a job target.

## SYNTAX

### LatestVersion (Default)
```
Get-AzureSqlJobContentDefinition -ContentName <String[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

### AllVersions
```
Get-AzureSqlJobContentDefinition -ContentName <String[]> [-AllVersions]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### Version
```
Get-AzureSqlJobContentDefinition -ContentName <String[]> -Version <Int32>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJobContentDefinition** cmdlet gets one or multiple content definitions that are run or applied across entities within a job target.

The definition includes either the T-SQL script for T-SQL content or the DACPAC URI for DACPAC content.

## EXAMPLES

### Example 1: Get all versioned content definitions for a given content name
```
PS C:\>Get-AzureSqlJobContentDefinition -ContentName "CreateMyTestTable"
CommandText                   ContentName                                   VersionNumber Comment
-----------                   -----------                                   ------------- -------
IF NOT EXISTS (SELECT name... CreateMyTestTable                                         1
```

This command gets all versioned content definitions for a given content name.

### Example 2: Get a specific versioned content definition for a given content name
```
PS C:\>Get-AzureSqlJobContentDefinition -ContentName "CreateMyTestTable" -Version 1
CommandText                   ContentName                                   VersionNumber Comment
-----------                   -----------                                   ------------- -------
IF NOT EXISTS (SELECT name... CreateMyTestTable                                         1
```

This command gets a specific versioned content definition for a given content name.

## PARAMETERS

### -AllVersions
Indicates that all versions of the content's definitions are returned.

```yaml
Type: SwitchParameter
Parameter Sets: AllVersions
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureSqlJobConnection
Specifies the connection state object for the job.
You can get the connection state object through the N[ew-AzureSqlJobConnection](./New-AzureSqlJobConnection.md) cmdlet.
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
Specifies the name of the content.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the particular version of content definition to return.

```yaml
Type: Int32
Parameter Sets: Version
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

[Set-AzureSqlJobContentDefinition](./Set-AzureSqlJobContentDefinition.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
