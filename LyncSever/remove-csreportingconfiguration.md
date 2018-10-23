---
title: Remove-CsReportingConfiguration
TOCTitle: Remove-CsReportingConfiguration
ms:assetid: 17cc1865-4bd9-4630-9947-2c432d1203b3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204711(v=OCS.15)
ms:contentKeyID: 49312136
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsReportingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes an existing collection of reporting configuration settings. Reporting configuration settings are used to specify the URL for installations of Lync Server 2013 Monitoring Reports. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsReportingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

In Example 1, the reporting configuration settings with the Identity service:MonitoringDatabase:atl-sql-002.litwareinc.com are removed.

    Remove-CsReportingConfiguration -Identity "service:MonitoringDatabase:atl-sql-002.litwareinc.com"

## Example 2

In Example 2, all the reporting configuration settings currently in use in the organization are removed. To do this, the command first uses the **Get-CsReportingConfiguration** cmdlet to return a collection of all the reporting configuration settings. This collection is then piped to the **Remove-CsReportingConfiguration** cmdlet, which removes each item in the collection.

    Get-CsReportingConfiguration | Remove-CsReportingConfiguration

## Example 3

The command shown in Example 3 deletes any reporting configuration settings where the reporting URL is set to https://atl-sql-002.litwareinc.com/lync\_reports. To carry out this task, the command first uses the **Get-CsReportingConfiguration** cmdlet to return all the reporting configuration settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the ReportingURL property is equal to https://atl-sql-002.litwareinc.com/lync\_reports. That filtered collection is then piped to the **Remove-CsReportingConfiguration** cmdlet, which removes each item in the collection.

    Get-CsReportingConfiguration | Where-Object {$_.ReportingUrl -eq "https://atl-sql-002.litwareinc.com/lync_reports" | Remove-CsReportingConfiguration

## Detailed Description

Reporting configuration settings are used to specify the home page for the Lync Server Monitoring Reports; if you are not using Monitoring Reports then there is no reason for you to modify the reporting configuration settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsReportingConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsReportingConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Service Identity of the monitoring database whose reporting configuration settings are to be removed. For example:</p>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsReportingConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration object.

## Return Types

None. Instead, the **Remove-CsReportingConfiguration** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsReportingConfiguration](get-csreportingconfiguration.md)  
[New-CsReportingConfiguration](new-csreportingconfiguration.md)  
[Set-CsReportingConfiguration](set-csreportingconfiguration.md)

