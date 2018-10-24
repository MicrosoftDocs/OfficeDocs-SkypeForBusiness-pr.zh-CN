---
title: New-CsReportingConfiguration
TOCTitle: New-CsReportingConfiguration
ms:assetid: 2f033456-5c1c-4313-ab17-37038a412189
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204787(v=OCS.15)
ms:contentKeyID: 49312379
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsReportingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of reporting configuration settings at the service scope. Reporting configuration settings are used to specify the URL used to access Lync Server 2013 Monitoring Reports. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsReportingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-ReportingUrl <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 creates a new collection of reporting configuration settings assigned to the monitoring database with the identity service:MonitoringDatabase:atl-sql-001.litwareinc.com. In this example, the value of the ReportingUrl property is set to "https://atl-sql-001.litwareinc.com/lync\_reports".

    New-CsReportingConfiguration -Identity "service:MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingUrl "https://atl-sql-001.litwareinc.com/lync_reports"

## Detailed Description

Reporting configuration settings are used to specify the home page for the Lync Server Monitoring Reports; if you are not using Monitoring Reports then there is no reason for you to modify the reporting configuration settings.

If you do not know the URL for the Monitoring Reports home page you can determine that URL by doing the following:

1.  Open the SQL Server Reporting Services Configuration Manager for the SQL Server instance that contains your monitoring database.

2.  In the Configuration Manager, click **Report Manager URL** and then click the URL for your Monitoring Reports. If you see two URLs, click the one that uses the https protocol.

3.  In SQL Server Reporting Services, click **LyncServerReports**.

4.  On the LyncServerReports page, click **Reports Home Page**. That will take you to the home page for the Monitoring Reports. You can then copy the URL and use that URL in conjunction with the CsReportingConfiguration cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsReportingConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **New-CsReportingConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Service Identity of the monitoring database to be associated with the new reporting configuration settings. For example:</p>
<p>-Identity &quot;Service:MonitoringDatabase:atl-sql-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>ReportingUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the Lync Server 2013 Monitoring Reports.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsReportingConfiguration** cmdlet does not accept pipelined data.

## Return Types

The **New-CsReportingConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsReportingConfiguration](get-csreportingconfiguration.md)  
[Remove-CsReportingConfiguration](remove-csreportingconfiguration.md)  
[Set-CsReportingConfiguration](set-csreportingconfiguration.md)

