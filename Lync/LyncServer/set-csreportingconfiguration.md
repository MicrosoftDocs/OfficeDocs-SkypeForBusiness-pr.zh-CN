---
title: Set-CsReportingConfiguration
TOCTitle: Set-CsReportingConfiguration
ms:assetid: 8e7c8e8c-ab68-4f95-a58e-b04a9b2110ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205075(v=OCS.15)
ms:contentKeyID: 49313556
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsReportingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies the reporting URL for an existing collection of reporting configuration settings. Reporting configuration settings are used to specify the URL used to access Lync Server 2013 Monitoring Reports. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsReportingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsReportingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-ReportingUrl <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 modifies the reporting URL for the reporting configuration settings with the Identity service:MonitoringDatabase:atl-sql-002.litwareinc.com. In this example, the reporting URL is changed to "https://atl-sql-002.litwareinc.com/lync\_reports".

    Set-CsReportingConfiguration -Identity "service:MonitoringDatabase:atl-sql-002.litwareinc.com" -ReportingURL "https://atl-sql-002.litwareinc.com/lync_reports"

## Detailed Description

Reporting configuration settings are used to specify the home page for the Lync Server Monitoring Reports; if you are not using Monitoring Reports then there is no reason for you to modify the reporting configuration settings.

If you do not know the URL for the Monitoring Reports home page you can determine that URL by doing the following:

1.  Open the SQL Server Reporting Services Configuration Manager for the SQL Server instance that contains your monitoring database.

2.  In the Configuration Manager, click **Report Manager URL** and then click the URL for your Monitoring Reports. If you see two URLs, click the one that uses the https protocol.

3.  In SQL Server Reporting Services, click **LyncServerReports**.

4.  On the LyncServerReports page, click **Reports Home Page**. That will take you to the home page for the Monitoring Reports. You can then copy the URL and use that URL in conjunction with the CsReportingConfiguration cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsReportingConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsReportingConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Service Identity of the monitoring database whose reporting configuration settings are being modified. For example:</p>
<p>-Identity &quot;Service:MonitoringDatabase:atl-sql-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
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

The **Set-CsReportingConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration object.

## Return Types

None. Instead, the **Set-CsReportingConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsReportingConfiguration](get-csreportingconfiguration.md)  
[New-CsReportingConfiguration](new-csreportingconfiguration.md)  
[Remove-CsReportingConfiguration](remove-csreportingconfiguration.md)

