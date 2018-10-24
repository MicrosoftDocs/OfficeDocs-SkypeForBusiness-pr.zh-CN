---
title: Install-CsDatabase
TOCTitle: Install-CsDatabase
ms:assetid: e91c1800-35f6-40ef-840d-7a518bddcae6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399044(v=OCS.15)
ms:contentKeyID: 49314608
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Install-CsDatabase

 

_**上一次修改主题：** 2015-03-09_

Installs one or more Lync Server databases. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Install-CsDatabase -LocalDatabases <SwitchParameter> [-ForDefaultInstance <SwitchParameter>] [-ForInstance <String>] <COMMON PARAMETERS>

    Install-CsDatabase -CentralManagementDatabase <SwitchParameter> -SqlServerFqdn <Fqdn> [-Backup <SwitchParameter>] [-Collocated <SwitchParameter>] [-SqlInstanceName <String>] <COMMON PARAMETERS>

    Install-CsDatabase -ConfiguredDatabases <SwitchParameter> -SqlServerFqdn <Fqdn> [-ExcludeCollocatedStores <SwitchParameter>] [-ForDefaultInstance <SwitchParameter>] [-ForInstance <String>] <COMMON PARAMETERS>

    Install-CsDatabase -DatabaseType <Application | Archiving | Monitoring | User | Provision | CentralAdmin | Lyss | Registrar | Edge | PersistentChat | PersistentChatCompliance | CentralMgmt> [-Collocated <SwitchParameter>] [-SqlInstanceName <String>] [-SqlServerFqdn <Fqdn>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Clean <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DatabasePathMap <Hashtable>] [-DatabasePaths <String[]>] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-NoReindex <SwitchParameter>] [-Report <String>] [-SkipPrepareCheck <SwitchParameter>] [-Update <SwitchParameter>] [-UseDefaultSqlPaths <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Install-CsDatabase** cmdlet reads in the Lync Server topology, and then installs any required databases on the pool atl-sql-001.litwareinc.com.

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com -DatabasePaths "E:\CSLog","F:\CSLog","G:\CSDB"

## EXAMPLE 2

The command shown in Example 2 installs the 中央管理存储 on the pool atl-sql-001.litwareinc.com. The database will be installed in the rtc instance, and make use of the folder G:\\CSDB.

    Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn atl-sql-001.litwareinc.com -SqlInstanceName rtc -DatabasePaths "G:\CSDB"

## Detailed Description

Lync Server makes extensive use of SQL Server databases, ranging from the 中央管理存储 to the 存档数据库. As a general rule, these databases are set up at the same time you install Lync Server or at the same time you install a Lync Server role (such as 监控服务器) that requires a database back end. After installation has taken place these databases typically will not need to be reinstalled or moved to new locations.

On rare occasions, however, you might need to manually install a Lync Server database; this could be because you need to move a database to another server, or because a setup-related problem failed to install the database for you. The **Install-CsDatabase** cmdlet provides a way for you to install any of the SQL Server databases used by Lync Server.

When running the **Install-CsDatabase** cmdlet there are basically three different ways to handle the configuration of the database being installed:

Option 1 -- Run the cmdlet without including a parameter that specifies the database paths. When the **Install-CsDatabase** cmdlet is run without the DatabasePath or the UseDefaultSqlPath parameter the cmdlet uses a built-on algorithm to choose the storage location for the database logs and data files. Note that this built-in algorithm works with a stand-alone SQL Server, it will not work with a SQL Server cluster. To install a database on a SQL Server cluster your command must include either the DatabasePath or the UseDefaultSqlPath parameter

Option 2 -- Run the cmdlet along with the DatabasePath parameter. When the **Install-CsDatabase** is cmdlet run with the DatabasePath parameter the built-in algorithm is not used to choose the storage location for the database logs and data files. Instead, administrators can select the location for these logs and data files. To install both data files and SQL Server logs in the same location, simply specify the path to the folder where this data should be stored. For example:

\-DatabasePath C:\\SqlData

To store data files in one location and log files in a second location, specify the path to each folder, separating the two locations by using a comma (be careful not to put a blank space before or after the comma):

\-DatabasePath C:\\SqlLogs,D:\\SqlData

The log files will always be stored on the first location specified, while data files will be stored in the second location.

In a pool backend, certain log files might be stored on a drive all by themselves. If you have a pool backend with a single drive, files will be distributed like this:

Drive 1 – Rtcdyn log; Rtc log; other logs; other data.

If you have two drives, files will be distributed like this:

Drive 1 – Rtcdyn log; Rtc log.

Drive 2 – Other logs; other data.

With three drives:

Drive 1 – Rtcdyn log.

Drive 2 – Rtc log.

Drive 3 – Other logs; other data.

And with four drives:

Drive 1 – Rtcdyn log.

Drive 2 – Rtc log.

Drive 3 – Other logs.

Drive 4 – Other data.

Option 3 -- Run the cmdlet along with the UseDefaultSqlPaths parameter. When the **Install-CsDatabase** cmdlet is run using the UseDefaultSqlPaths parameter, the built-in algorithm is not used to choose the storage locations for the database logs and data files. Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator). Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.

Before running the **Install-CsDatabase** cmdlet you should make sure that the RTCUniversalServerAdmins groups has not been assigned as the database owner. If that group is listed as the owner the group could possibly be deleted when you call the **Install-CsDatabase** cmdlet.

Who can run this cmdlet: You must be a member of the domain, a member of the RTCUniversalReadOnlyAdmins group, a SQL Server administrator, and a local administrator on the computer where SQL Server is installed in order to run the **Install-CsDatabase** cmdlet locally. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Install-CsDatabase"}

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
<td><p><em>CentralManagementDatabase</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If this parameter is included, the <strong>Install-CsDatabase</strong> cmdlet will use the SqlServerFqdn parameter to install the 中央管理存储 on the specified computer. This parameter is typically used only by 拓扑生成器, and is generally called just once, during initial setup.</p></td>
</tr>
<tr class="even">
<td><p><em>ConfiguredDatabases</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Reads information from the Lync Server topology, and installs the required databases on the specified SQL Server computer or SQL Server cluster. Administrators who need to call the <strong>Install-CsDatabase</strong> cmdlet will almost always use this parameter when specifying the databases to be installed.</p></td>
</tr>
<tr class="odd">
<td><p><em>DatabaseType</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.DatabaseNameType</p></td>
<td><p>Enables you to install a specific database on a specific SQL Server computer or SQL Server cluster. As a general rule, administrators should not run the <strong>Install-CsDatabase</strong> cmdlet with the DatabaseType parameter unless instructed otherwise by Microsoft support personnel. Instead, administrators should typically use the ConfiguredDatabases parameter. The DatabaseType parameter requires you to know the exact type and location for every database used in your topology, and is only required if the <strong>Install-CsDatabase</strong> cmdlet command fails to run using the ConfiguredDatabases parameter.</p>
<p>Valid values for DatabaseType are:</p>
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
<tr class="even">
<td><p><em>LocalDatabases</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If this parameter is included, the <strong>Install-CsDatabase</strong> cmdlet will read in the Lync Server topology and install databases and stores as needed on the local computer.</p></td>
</tr>
<tr class="odd">
<td><p><em>SqlServerFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the computer where the database is to be installed. For example: -SqlServerFqdn atl-sql-001.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>Backup</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When used, backs up the existing Central Management server database to the specified SQL Server instance.</p></td>
</tr>
<tr class="odd">
<td><p><em>Clean</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If this parameter is included, the <strong>Install-CsDatabase</strong> cmdlet will delete and reinstall databases as needed. If this parameter is not included, the <strong>Install-CsDatabase</strong> cmdlet will not overwrite any existing databases. You cannot use both Clean and Update in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Collocated</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, additional database roles will be collocated with the 中央管理存储.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DatabasePathMap</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Collections.Hashtable</p></td>
<td><p>Enables you to specify custom folder paths for data files and log files; multiple paths should be separated by using a semicolon (;). For example:</p>
<p>-DatabasePathMap @{&quot;Archiving:DbPath&quot;=&quot;\\atl-sql-001.litwareinc.com\db&quot;;&quot;Archiving:LogPath&quot;=&quot;\\atl-sql-002.litwareinc.com\logs&quot;}</p></td>
</tr>
<tr class="odd">
<td><p><em>DatabasePaths</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Specifies the drives and folders where data and log files can be stored; for example: -DatabasePaths &quot;D:\Logs&quot;,&quot;E:\Data&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>ExcludeCollocatedStores</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, suppresses a warning message telling you that any collocated database stores must be installed on the local computer.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, forces the installation of the new database even if an existing database of that type is currently in use.</p></td>
</tr>
<tr class="even">
<td><p><em>ForDefaultInstance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, instructs the <strong>Install-CsDatabase</strong> cmdlet to only act against the default SQL Server instance. You cannot use both ForDefaultInstance and ForInstance in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>ForInstance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When specified, instructs the <strong>Install-CsDatabase</strong> cmdlet to only act against the specified SQL Server instance. You cannot use both ForInstance and ForDefaultInstance in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of a global catalog server in your domain. This parameter is not required if you are running the <strong>Install-CsDatabase</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of a domain controller where global settings are stored. If global settings are stored in the System container in Active Directory 域服务, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="even">
<td><p><em>NoReindex</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prevents the index files from being rebuilt when a database is being updated. This parameter can only be used along with the Update parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\InstallDatabases.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>SkipPrepareCheck</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, causes the <strong>Install-CsDatabase</strong> cmdlet to forego its initial preparation checks.</p></td>
</tr>
<tr class="odd">
<td><p><em>SqlInstanceName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the database instance where the database is to be installed. A database instance is simply a set of running processes that provides access to database files. If this parameter is omitted, the <strong>Install-CsDatabase</strong> cmdlet will use the default SQL Server instance.</p></td>
</tr>
<tr class="even">
<td><p><em>Update</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, updates the existing database. You cannot use Update and Clean in the same command.</p>
<p>Note that the Update parameter cannot be used against mirrored databases; the command will fail because the mirror databases cannot be dropped and recreated. To use the Update parameter with mirrored databases you must first use the <a href="uninstall-csmirrordatabase.md">Uninstall-CsMirrorDatabase</a> cmdlet to disassociate the mirrored databases. At that point you can then run Install-CsDatabase and the Update parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseDefaultSqlPaths</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, instructs SQL Server to select the drive where data and log files will be stored.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Install-CsDatabase** cmdlet does not accept pipelined input.

## Return Types

The **Install-CsDatabase** cmdlet does not return any values or objects.

## 另请参阅

#### 其他资源

[Uninstall-CsDatabase](uninstall-csdatabase.md)

