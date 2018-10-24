---
title: Install-CsMirrorDatabase
TOCTitle: Install-CsMirrorDatabase
ms:assetid: 6e3acdfb-39da-4aa4-b125-1ea542971da3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204986(v=OCS.15)
ms:contentKeyID: 49313189
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Install-CsMirrorDatabase

 

_**上一次修改主题：** 2015-03-09_

Associates a mirror database with a Lync Server 2013 database. A database mirror enables you to simultaneously maintain two copies of a database, each copy residing on a different server. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Install-CsMirrorDatabase -ConfiguredDatabases <SwitchParameter> -SqlServerFqdn <Fqdn> [-ForDefaultInstance <SwitchParameter>] [-ForInstance <String>] <COMMON PARAMETERS>

    Install-CsMirrorDatabase -DatabaseType <Application | Archiving | Monitoring | User | Provision | CentralAdmin | Lyss | Registrar | Edge | PersistentChat | PersistentChatCompliance | CentralMgmt> -SqlServerFqdn <Fqdn> [-SqlInstanceName <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -FileShare <String> [-Confirm [<SwitchParameter>]] [-DatabasePathMap <Hashtable>] [-DropExistingDatabasesOnMirror <SwitchParameter>] [-ExcludeDatabaseList <String[]>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 installs any predefined database. The ConfiguredDatabases parameter causes the **Install-CsMirrorDatabase** cmdlet to use the current topology to determine which databases should be.

    Install-CsMirrorDatabase -ConfiguredDatabases -FileShare "\\atl-fs-001\DbBackup" -SqlServerFqdn "atl-primary-001.litwareinc.com" -DropExisitingDatabasesOnMirror

## Detailed Description

Mirror databases enable you to simultaneously maintain two copies of a database: when data is written to Database A, a copy of that data is also written to its mirror database. This provides the ability to instantly replace Database A should that database become unavailable: you can “failover” to the mirror database with minimal disruption to your users and with minimal data loss. After you have installed your primary databases you can then install and configure mirror databases by using the **Install-CsMirrorDatabase** cmdlet.

By default, the **Install-CsMirrorDatabase** cmdlet installs and configures mirror databases for all the Lync Server databases housed on the specified server. However, you can use the DatabaseType or the ExcludeDatabaseList parameters to specify exactly which mirror databases should or should not be installed. DatabaseType enables you to specify only the databases that should be installed; ExcludeDatabaseList lets you specify the databases that should not be installed.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Install-CsMirrorDatabase"}

Lync Server 控制面板: The functions carried out by the **Install-CsMirrorDatabase** cmdlet are not available in the Lync Server 控制面板.

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>ConfiguredDatabases</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Reads information from the Lync Server topology, and installs the required mirror databases on the specified SQL Server computer or SQL Server cluster.</p></td>
</tr>
<tr class="even">
<td><p><em>DatabaseType</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.DatabaseNameType</p></td>
<td><p>Type of mirror database to be installed. Allowed values are:</p>
<p>Application</p>
<p>Archiving</p>
<p>CentralAdmin</p>
<p>CentralMgmt</p>
<p>Edge</p>
<p>Lyss</p>
<p>Monitoring</p>
<p>PersistentChat</p>
<p>PersistentChatCompliance</p>
<p>Provision</p>
<p>Registrar</p>
<p>User</p></td>
</tr>
<tr class="odd">
<td><p><em>FileShare</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>UNC path to the database shared folder. The file share is used to export of databases from the primary SQL Server and import those databases onto the mirror.</p>
<p>The shared folder and its contents can be deleted after mirroring is established. The folder should also be deleted if you decide to disable mirroring.</p></td>
</tr>
<tr class="even">
<td><p><em>SqlServerFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the primary SQL Server computer. For example:</p>
<p>-SqlServerFqdn atl-sql-001.litwareinc.com</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>DatabasePathMap</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Collections.Hashtable</p></td>
<td><p>Enables you to specify custom folder paths for data files and log files; multiple paths should be separated by using a semicolon (;). For example:</p>
<p>-DatabasePathMap @{&quot;Archiving:DbPath&quot;=&quot;\\atl-sql-001.litwareinc.com\db&quot;;&quot;Archiving:LogPath&quot;=&quot;\\atl-sql-002.litwareinc.com\logs&quot;}</p></td>
</tr>
<tr class="odd">
<td><p><em>DropExistingDatabasesOnMirror</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, deletes any existing copies of the mirrored databases from the server acting as the mirror before new data is copied to that server.</p></td>
</tr>
<tr class="even">
<td><p><em>ExcludeDatabaseList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>List of databases that should not be included in the mirror database; multiple databases can be specified by separating those databases using commas. For example:</p>
<p>-ExcludeDatabaseList &quot;RTCCAB&quot;,&quot;RTCPROV&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>ForDefaultInstance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, instructs the <strong>Install-CsMirrorDatabase</strong> cmdlet to only act against the default SQL Server instance. You cannot use both ForDefaultInstance and ForInstance in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>ForInstance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When specified, instructs the <strong>Install-CsMirrorDatabase</strong> cmdlet to only act against the specified SQL Server instance. You cannot use both ForInstance and ForDefaultInstance in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -</p>
<p>Report &quot;C:\Logs\InstallDatabaseMirror.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>SqlInstanceName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the database instance where the database is to be installed. A database instance is simply a set of running processes that provides access to database files. If this parameter is omitted, the <strong>Install-CsMirrorDatabase</strong> cmdlet will use the default SQL Server instance.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Install-CsMirrorDatabase** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Get-CsDatabaseMirrorState](get-csdatabasemirrorstate.md)  
[Uninstall-CsMirrorDatabase](uninstall-csmirrordatabase.md)

