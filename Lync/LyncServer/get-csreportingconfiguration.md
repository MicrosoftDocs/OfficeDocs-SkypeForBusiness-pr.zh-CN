---
title: Get-CsReportingConfiguration
TOCTitle: Get-CsReportingConfiguration
ms:assetid: e777a154-354a-49da-8140-79f80416bc49
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205356(v=OCS.15)
ms:contentKeyID: 49314573
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsReportingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the reporting configuration settings in use in the organization. Reporting configuration settings are used to specify the URL used for accessing Lync Server 2013 Monitoring Reports. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsReportingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsReportingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information for all the reporting configuration settings currently in use in the organization.

    Get-CsReportingConfiguration

## Example 2

In Example 2, information is returned for a single collection of reporting configuration settings: the settings with the Identity "Service:MonitoringDatabase:atl-sql-001.litwareinc.com".

    Get-CsReportingConfiguration -Identity "Service:MonitoringDatabase:atl-sql-001.litwareinc.com"

## Example 3

In Example 3, information is returned for all the reporting configuration settings that have an Identity that ends in ".litwareinc.com". To do this, the command uses the Filter parameter and the filter value "\*.litwareinc.com".

    Get-CsReportingConfiguration -Filter "*.litwareinc.com"

## Example 4

Example 4 returns information for all the reporting configuration settings that include the string value "\_ARCHINST" somewhere in their reporting URL. To do this the command first uses the **Get-CsReportingConfiguration** cmdlet to return a collection of all the reporting configuration settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the ReportingUrl includes (-like) the string value "\_ARCHINST".

    Get-CsReportingConfiguration | Where-Object {$_.ReportingUrl -like "*_ARCHINST*"}

## Detailed Description

Reporting configuration settings are used to specify the home page for the Lync Server Monitoring Reports; if you are not using Monitoring Reports then there is no reason for you to modify the reporting configuration settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsReportingConfiguration

**Lync Server 控制面板:** The functions carried out by the **Get-CsReportingConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters when specifying the reporting configuration settings to be returned. For example, this syntax returns all the settings configured at the service scope:</p>
<p>-Filter &quot;service:*&quot;</p>
<p>Note that you cannot use both the Filter and the Identity parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Service Identity of the monitoring database associated with the reporting configuration settings. For example:</p>
<p>-Identity &quot;Service:MonitoringDatabase:atl-sql-001.litwareinc.com&quot;</p>
<p>If you do not include either the Identity parameter or the Filter parameter in your command, then the <strong>Get-CsReportingConfiguration</strong> cmdlet will return all the reporting configuration settings in use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the reporting configuration data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsReportingConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsReportingConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration object.

## 另请参阅

#### 其他资源

[New-CsReportingConfiguration](new-csreportingconfiguration.md)  
[Remove-CsReportingConfiguration](remove-csreportingconfiguration.md)  
[Set-CsReportingConfiguration](set-csreportingconfiguration.md)

